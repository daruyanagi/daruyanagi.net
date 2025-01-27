---
date: 2017-06-27T02:17:36.0000000
draft: false
title: "空の ASP.NET Core プロジェクトからとりあえず Web サイトのトップページを書いて Azure にデプロイするまで"
tags: ["Microsoft Azure", "ASP.NET Core"]
eyecatch: 20170627010541.png
---
<p><span itemscope itemtype="http://schema.org/Photograph"><img src="20170627010541.png" alt="f:id:daruyanagi:20170627010541p:plain" title="f:id:daruyanagi:20170627010541p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>ウチの Web サイトは Microsoft Azure の Bizspark を使わせてもらっていたのですが、いつのまにかサブスクリプションが切れていて（そういえばいろいろメールがきてた気がしないでもない）、アクセスできなくなってしまいました。あれ、データもサルベージできないのかな……。</p><p>というわけで、一からサイトを作り直すことにしました。</p><p>とりあえず、今回の目標は web.archive.org からサルベージしたトップページの復旧です。もう一度 ASP.NET で組みなおしてもいいのですが、いい機会なので、ずっと挑戦してみたかった ASN.NET Core を利用してみることにしましょう（よく知らんけど、今後はこっちが主流になりそうな匂いがするので）。右も左も分からんけど、大丈夫やろうか。</p>

<div class="section">
<h3>前提条件と大まかな流れ</h3>
<p>まず Visual Studio 2017 Community の「ASP.NET と Web 開発」というワークロードがインストールされている環境を用意（これだけで足りんかったらごめんな、正直よくわかってないんや）。空のテンプレートを作成し、トップページの Index.cshtml を表示するところまで頑張ります。</p>

</div>
<div class="section">
<h3>実装</h3>

<div class="section">
<h4>空のテンプレートを作成</h4>
<p><span itemscope itemtype="http://schema.org/Photograph"><img src="20170627011714.png" alt="f:id:daruyanagi:20170627011714p:plain" title="f:id:daruyanagi:20170627011714p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>まず、「ASP.NET Core Web アプリケーション」のプロジェクトを新規に作成します（名前は Sample にしました）。</p>

<ul>
<li>.NET Core</li>
<li>.NET Framework</li>
</ul><p>の 2 つのバージョンがありますが、今回は前者（.NET Core）を選択。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20170627022120.png" alt="f:id:daruyanagi:20170627022120p:plain" title="f:id:daruyanagi:20170627022120p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>.NET Core はクロスプラットフォームなので、Linux サーバーでも運用できるはず。いずれは Docker なんかも試してみたいなー。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20170627012047.png" alt="f:id:daruyanagi:20170627012047p:plain" title="f:id:daruyanagi:20170627012047p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>プロジェクトを作成するとテンプレート画面が現れるので、「空」を選択。いきなり訳の分からんファイルをブリブリ生成されても泣いてしまうからね、仕方ないね。</p><p>ちなみに ASP.NET Core のバージョンは 1.1 でした。そろそろ 2.0 なんじゃなかったっけ？　また変わったら嫌だなー。</p>

</div>
<div class="section">
<h4>空のテンプレートを概観</h4>
<p><span itemscope itemtype="http://schema.org/Photograph"><img src="20170627012316.png" alt="f:id:daruyanagi:20170627012316p:plain" title="f:id:daruyanagi:20170627012316p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>プロジェクトが作成されたら、さらっと中身を見てみましょう。ファイル構造はこんな感じです</p>

<ul>
<li>wwwroot フォルダー</li>
<li>Program.cs</li>
<li>Startup.cs</li>
</ul><p>シンプルでいい感じ。最初に実行される main() 関数は Program.cs に記述されています。</p>
<pre class="code lang-cs" data-lang="cs" data-unlink><span class="synStatement">using</span> System;
<span class="synStatement">using</span> System.Collections.Generic;
<span class="synStatement">using</span> System.IO;
<span class="synStatement">using</span> System.Linq;
<span class="synStatement">using</span> System.Threading.Tasks;
<span class="synStatement">using</span> Microsoft.AspNetCore.Hosting;

<span class="synType">namespace</span> Sample
{
<span class="synType">public</span> <span class="synType">class</span> Program
{
<span class="synType">public</span> <span class="synType">static</span> <span class="synType">void</span> Main(<span class="synType">string</span>[] args)
{
var host = <span class="synStatement">new</span> WebHostBuilder()
.UseKestrel()
.UseContentRoot(Directory.GetCurrentDirectory())
.UseIISIntegration()
.UseStartup&lt;Startup&gt;()
.UseApplicationInsights()
.Build();

host.Run();
}
}
}
</pre><p>よくわからんけど、いろんな設定をしてホストを作成し、実行しているみたいですね。素人は触らん方がよさそう。</p><p>一方の Startup.cs はこんな感じ。</p>
<pre class="code lang-cs" data-lang="cs" data-unlink><span class="synStatement">using</span> System;
<span class="synStatement">using</span> System.Collections.Generic;
<span class="synStatement">using</span> System.Linq;
<span class="synStatement">using</span> System.Threading.Tasks;
<span class="synStatement">using</span> Microsoft.AspNetCore.Builder;
<span class="synStatement">using</span> Microsoft.AspNetCore.Hosting;
<span class="synStatement">using</span> Microsoft.AspNetCore.Http;
<span class="synStatement">using</span> Microsoft.Extensions.DependencyInjection;
<span class="synStatement">using</span> Microsoft.Extensions.Logging;

<span class="synType">namespace</span> Sample
{
<span class="synType">public</span> <span class="synType">class</span> Startup
{
<span class="synComment">// This method gets called by the runtime. Use this method to add services to the container.</span>
<span class="synComment">// For more information on how to configure your application, visit https://go.microsoft.com/fwlink/?LinkID=398940</span>
<span class="synType">public</span> <span class="synType">void</span> ConfigureServices(IServiceCollection services)
{
}

<span class="synComment">// This method gets called by the runtime. Use this method to configure the HTTP request pipeline.</span>
<span class="synType">public</span> <span class="synType">void</span> Configure(IApplicationBuilder app, IHostingEnvironment env, ILoggerFactory loggerFactory)
{
loggerFactory.AddConsole();

<span class="synStatement">if</span> (env.IsDevelopment())
{
app.UseDeveloperExceptionPage();
}

app.Run(async (context) =&gt;
{
await context.Response.WriteAsync(<span class="synConstant">&quot;Hello World!&quot;</span>);
});
}
}
}
</pre><p>ConfigureServices と Configure という二つのメソッドがあり、Configure で Hello World! を出力する（context.Response.WriteAsync）ようになっているみたい。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20170627012904.png" alt="f:id:daruyanagi:20170627012904p:plain" title="f:id:daruyanagi:20170627012904p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>実際に［F5］キーで実行してみると、Hello World! が出力されました。つまり、どっかにファイルを置いて読み込み、context.Response.WriteAsync() すれば、とりあえずトップページは出力されそう……だけど、後々のことを考えると流石にそれはめんどくさそうなので、フレームワークの力を借りておこうかな。</p>

</div>
<div class="section">
<h4>ASP.NET Core MVC の導入</h4>
<p>できれば使い慣れた ASP.NET Web Pages の ASN.NET Core 版のようなのがあればよかったのだけど、今のところ無いのかな？　よくわかんないので、比較的情報の多かった ASN.NET Core MVC を導入してみます。NuGet パッケージで簡単にインストールできるみたいなので、今回はそれを利用してみましょう。</p><p>アプリを終了して、ソリューションのコンテキストメニューから［ソリューションの NuGet パッケージを管理］コマンドを選択。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20170627013555.png" alt="f:id:daruyanagi:20170627013555p:plain" title="f:id:daruyanagi:20170627013555p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>「Microsoft.AspNetCore.MVC」を探してインストールします。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20170627013752.png" alt="f:id:daruyanagi:20170627013752p:plain" title="f:id:daruyanagi:20170627013752p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>パッケージがクソほどあってビビるけど、インストールは一瞬で終わりました。</p>
<pre class="code" data-lang="" data-unlink>：
：
&#39;Microsoft.Extensions.WebEncoders 1.1.2&#39; が Sample に正常にインストールされました
NuGet の操作の実行に 2.22 sec かかりました
経過した時間: 00:00:04.0184836
========== 終了 ==========

NuGet パッケージを復元しています...
経過した時間: 00:00:01.3445620
========== 終了 ==========</pre><p>最近の NuGet は速いなー……なんかもっと遅いイメージあったんだけど。あとは、Startup.cs で MVC を利用するよう書き換えます。</p>
<pre class="code lang-cs" data-lang="cs" data-unlink><span class="synStatement">using</span> System;
<span class="synStatement">using</span> System.Collections.Generic;
<span class="synStatement">using</span> System.Linq;
<span class="synStatement">using</span> System.Threading.Tasks;
<span class="synStatement">using</span> Microsoft.AspNetCore.Builder;
<span class="synStatement">using</span> Microsoft.AspNetCore.Hosting;
<span class="synStatement">using</span> Microsoft.AspNetCore.Http;
<span class="synStatement">using</span> Microsoft.Extensions.DependencyInjection;
<span class="synStatement">using</span> Microsoft.Extensions.Logging;

<span class="synType">namespace</span> Sample
{
<span class="synType">public</span> <span class="synType">class</span> Startup
{
<span class="synComment">// This method gets called by the runtime. Use this method to add services to the container.</span>
<span class="synComment">// For more information on how to configure your application, visit https://go.microsoft.com/fwlink/?LinkID=398940</span>
<span class="synType">public</span> <span class="synType">void</span> ConfigureServices(IServiceCollection services)
{
<span class="synComment">// MVC を追加</span>
services.AddMvc();
}

<span class="synComment">// This method gets called by the runtime. Use this method to configure the HTTP request pipeline.</span>
<span class="synType">public</span> <span class="synType">void</span> Configure(IApplicationBuilder app, IHostingEnvironment env, ILoggerFactory loggerFactory)
{
loggerFactory.AddConsole();

<span class="synStatement">if</span> (env.IsDevelopment())
{
app.UseDeveloperExceptionPage();
}

<span class="synComment">// 使わないのでコメントアウト</span>
<span class="synComment">// app.Run(async (context) =&gt;</span>
<span class="synComment">// {</span>
<span class="synComment">//     await context.Response.WriteAsync(&quot;Hello World!&quot;);</span>
<span class="synComment">// });</span>

<span class="synComment">// ルーティング を追加</span>
app.UseMvc(routes =&gt;
{
routes.MapRoute(
<span class="synStatement">                name:</span> <span class="synConstant">&quot;default&quot;</span>,
<span class="synStatement">                template:</span> <span class="synConstant">&quot;{controller=Home}/{action=Index}/{id?}&quot;</span>);
});
}
}
}
</pre><p>ビルドしてエラーがなければ次に進みます。ルーティングのマップは、</p>

<ul>
<li>/Hoge/Fuga/Piyo</li>
</ul><p>にアクセスしたら、</p>

<ul>
<li>HogeController の Fuga() メソッドを叩け（引数は Piyo）</li>
</ul><p>って感じの意味だと思います。デフォルト引数（？）が設定されているので、ルートへのアクセスで</p>

<ul>
<li>HomeController の Index() メソッドを叩け</li>
</ul><p>になります。Index() メソッドでビューを表示できれば今回の目標は完了やね。――というわけで、次はコントローラーと、それを表示するビューの実装です。</p>

</div>
</div>
<div class="section">
<h3>コントローラーとビューを作成</h3>
<p><span itemscope itemtype="http://schema.org/Photograph"><img src="20170627015130.png" alt="f:id:daruyanagi:20170627015130p:plain" title="f:id:daruyanagi:20170627015130p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>以下のような構造でコントローラーとビューを作成します。この辺りは MVC の“お約束”なので覚えるしかない。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20170627021309.png" alt="f:id:daruyanagi:20170627021309p:plain" title="f:id:daruyanagi:20170627021309p:plain" class="hatena-fotolife" itemprop="image"></span><br />
</p>

<ul>
<li><b>Controllers フォルダー</b>
<ul>
<li><b>HomeController.cs</b></li>
</ul></li>
<li><b>Views フォルダー</b>
<ul>
<li><b>Home フォルダー</b>
<ul>
<li><b>Index.cshtml</b></li>
</ul></li>
</ul></li>
<li>wwwroot フォルダー</li>
<li>Program.cs</li>
<li>Startup.cs</li>
</ul><p>ソリューションエクスプローラーのコンテキストメニューには［追加］－［コントローラー］というコマンドがあるのですが、これを使うとなんかエラーが出たので、［新しい項目］コマンドからコントローラーを追加しました。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20170627015202.png" alt="f:id:daruyanagi:20170627015202p:plain" title="f:id:daruyanagi:20170627015202p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>先程、ルーティングでデフォルトコントローラーの名前を“Home”にしておいたのにはとくに意味はなく、単にこのときの既定の名前が“HomeController.cs”だったからデス。名前はお好みで。</p>
<pre class="code lang-cs" data-lang="cs" data-unlink><span class="synStatement">using</span> System;
<span class="synStatement">using</span> System.Collections.Generic;
<span class="synStatement">using</span> System.Linq;
<span class="synStatement">using</span> System.Threading.Tasks;
<span class="synStatement">using</span> Microsoft.AspNetCore.Mvc;

<span class="synComment">// For more information on enabling MVC for empty projects, visit https://go.microsoft.com/fwlink/?LinkID=397860</span>

<span class="synType">namespace</span> Sample.Controllers
{
<span class="synType">public</span> <span class="synType">class</span> HomeController : Controller
{
<span class="synComment">// GET: /&lt;controller&gt;/</span>
<span class="synType">public</span> IActionResult Index()
{
<span class="synStatement">return</span> View();
}
}
}
</pre><p>Index() も用意されているので、ここで追加のコーディングは不要。なんでも既定（“お約束”）に合わせておくと色々楽ちん。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20170627015533.png" alt="f:id:daruyanagi:20170627015533p:plain" title="f:id:daruyanagi:20170627015533p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>ビューもおんなじ感じで。作成するやで。ビューは殺風景なので、適当にサンプルを書いてみました。</p>
<pre class="code lang-cs" data-lang="cs" data-unlink>@{
var message = <span class="synConstant">&quot;Hello! World&quot;</span>;
}

&lt;html&gt;
&lt;head&gt;
&lt;title&gt;@message&lt;/title&gt;
&lt;/head&gt;
&lt;body&gt;
&lt;p&gt;@message&lt;/p&gt;

&lt;p&gt;@DateTime.Now&lt;/p&gt;
&lt;/body&gt;
&lt;/html&gt;
</pre><p>［F5］で実行します。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20170627015831.png" alt="f:id:daruyanagi:20170627015831p:plain" title="f:id:daruyanagi:20170627015831p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>フーーーッ！　これでだいたい完了！　あとはビューをしこしこ書いていくだけです。</p>

<div class="section">
<h4><s>性的</s>静的ファイルを利用</h4>
<p>けれど、これだけだと CSS や JavaScript を置いて読み込んだりできなくて不便でした。というわけで、以下の設定を Startup.cs の Configure() メソッドに追加しておきました（もうネームスペースやクラスの部分は省いて大丈夫ですよね！）。</p>
<pre class="code lang-cs" data-lang="cs" data-unlink><span class="synType">public</span> <span class="synType">void</span> Configure(IApplicationBuilder app, IHostingEnvironment env, ILoggerFactory loggerFactory)
{
loggerFactory.AddConsole();

<span class="synStatement">if</span> (env.IsDevelopment())
{
app.UseDeveloperExceptionPage();
}

<span class="synComment">// 以下の2行を追加</span>
app.UseDefaultFiles();
app.UseStaticFiles();

app.UseMvc(routes =&gt;
{
routes.MapRoute(
<span class="synStatement">        name:</span> <span class="synConstant">&quot;default&quot;</span>,
<span class="synStatement">        template:</span> <span class="synConstant">&quot;{controller=Home}/{action=Index}/{id?}&quot;</span>);
});
}
</pre><p>これで wwwroot に静的ファイルがあるかどうかをチェックし、あればそっちを先に読み込んでくれます。ビューを cshtml にする必要がなければ、html にして wwwroot に置いておき、この二行を追加するだけでもよかったね。……まぁ、今後のことも考えると無駄ではないけど。</p>

</div>
<div class="section">
<h4>デプロイ</h4>
<p><span itemscope itemtype="http://schema.org/Photograph"><img src="20170627020507.png" alt="f:id:daruyanagi:20170627020507p:plain" title="f:id:daruyanagi:20170627020507p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>プロジェクトのコンテキストメニューから［公開］コマンドを選択。あとはそんなに難しくないと思うで、以下省略。ウチの場合はトラブルなく、デプロイまで完了しました。いずれは GitHub 連携でデプロイ……みたいな感じにしたいですね。</p><p>終わり！</p>

</div>
</div>