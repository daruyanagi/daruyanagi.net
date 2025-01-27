---
date: 2017-08-15T04:36:34.0000000
draft: false
title: "空のアプリケーションから ASP.NET Core Razor Page を始める"
tags: ["ASP.NET Core Razor Page"]
eyecatch: 20170815033116.png
---
<p><span itemscope itemtype="http://schema.org/Photograph"><img src="20170815033116.png" alt="f:id:daruyanagi:20170815033116p:plain" title="f:id:daruyanagi:20170815033116p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>前回は ASP.NET Core Razor Page をチラ見してみましたが、ひな型（サンプル）プロジェクトが割とゴツい。これでは全体的な見通しが悪くて理解が進まないし、また<i>「Razor Pages はカンタン！」</i>というのも伝わりにくいと思いました。</p><p><iframe src="https://hatenablog-parts.com/embed?url=http%3A%2F%2Fblog.daruyanagi.jp%2Fentry%2F2017%2F08%2F15%2F032010" title="Visual Studio 2017.3 が出たっぽいので、ASP.NET Core Razor Pages をチラ見してみる - だるろぐ" class="embed-card embed-blogcard" scrolling="no" frameborder="0" style="display: block; width: 100%; height: 190px; max-width: 500px; margin: 10px 0px;"></iframe><cite class="hatena-citation"><a href="http://blog.daruyanagi.jp/entry/2017/08/15/032010">blog.daruyanagi.jp</a></cite></p><p>そこで、今回は Visual Studio 2017.3 を利用して“空”のアプリケーションから Razor Pages で Hello! World するまでをステップバイステップでやっていこうかなと思います。</p>

<div class="section">
<h3>空のアプリケーションを作成する</h3>
<p><span itemscope itemtype="http://schema.org/Photograph"><img src="20170815033122.png" alt="f:id:daruyanagi:20170815033122p:plain" title="f:id:daruyanagi:20170815033122p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>まず、［新しいプロジェクト］コマンドで .NET Core、ASP.NET Core Web アプリケーションを作成。フレームワークを .NET Core へ、.NET のバージョンを 2.0.0 に切り替えて、“空”のアプリケーションを作成します。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20170815033129.png" alt="f:id:daruyanagi:20170815033129p:plain" title="f:id:daruyanagi:20170815033129p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>このアプリケーションには、ソリューションファイルなどを除くと</p>

<ul>
<li>Program.cs</li>
<li>Startup.cs</li>
<li>静的ファイルを置く wwwroot フォルダー</li>
</ul><p>の3つしかありません。シンプルだね！　コードも最低限で、</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20170815033136.png" alt="f:id:daruyanagi:20170815033136p:plain" title="f:id:daruyanagi:20170815033136p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>［F5］キーで実行すると“Hello! World”が表示されるだけです。まずはここから始めましょう。</p>

</div>
<div class="section">
<h3>Program.cs と Startup.cs</h3>
<p>Program.cs は、アプリケーションを実行する際、最初に処理されます（エントリポイントってやつだな）。</p>
<pre class="code lang-cs" data-lang="cs" data-unlink><span class="synStatement">using</span> Microsoft.AspNetCore;
<span class="synStatement">using</span> Microsoft.AspNetCore.Hosting;

<span class="synType">namespace</span> WebApplication3
{
<span class="synType">public</span> <span class="synType">class</span> Program
{
<span class="synType">public</span> <span class="synType">static</span> <span class="synType">void</span> Main(<span class="synType">string</span>[] args)
{
BuildWebHost(args).Run();
}

<span class="synType">public</span> <span class="synType">static</span> IWebHost BuildWebHost(<span class="synType">string</span>[] args) =&gt;
WebHost.CreateDefaultBuilder(args)
.UseStartup&lt;Startup&gt;()
.Build();
}
}
</pre><p>WebHost をビルドして実行しているようですが、よくわかんないし、今回はとりあえずそのままにしておいていいです。</p><p>一方、Startup.cs は初期化を担当しています。空のアプリケーションの場合はこんな感じになっています。</p>
<pre class="code lang-cs" data-lang="cs" data-unlink><span class="synStatement">using</span> Microsoft.AspNetCore.Builder;
<span class="synStatement">using</span> Microsoft.AspNetCore.Hosting;
<span class="synStatement">using</span> Microsoft.AspNetCore.Http;
<span class="synStatement">using</span> Microsoft.Extensions.DependencyInjection;

<span class="synType">namespace</span> WebApplication3
{
<span class="synType">public</span> <span class="synType">class</span> Startup
{
<span class="synType">public</span> <span class="synType">void</span> ConfigureServices(IServiceCollection services)
{

}

<span class="synType">public</span> <span class="synType">void</span> Configure(IApplicationBuilder app, IHostingEnvironment env)
{
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
</pre><p>リクエストがあったらレスポンスに“Hello! World”と書いて送るだけのようです。</p>

</div>
<div class="section">
<h3>Razor Pages を使う</h3>
<p>Razor Pages は MVC に含まれています。なので、まず Startup.cs で MVC を有効にします。</p>
<pre class="code lang-cs" data-lang="cs" data-unlink><span class="synType">namespace</span> WebApplication3
{
<span class="synType">public</span> <span class="synType">class</span> Startup
{
<span class="synComment">// This method gets called by the runtime. Use this method to add services to the container.</span>
<span class="synComment">// For more information on how to configure your application, visit https://go.microsoft.com/fwlink/?LinkID=398940</span>
<span class="synType">public</span> <span class="synType">void</span> ConfigureServices(IServiceCollection services)
{
services.AddMvc();
}

<span class="synComment">// This method gets called by the runtime. Use this method to configure the HTTP request pipeline.</span>
<span class="synType">public</span> <span class="synType">void</span> Configure(IApplicationBuilder app, IHostingEnvironment env)
{
<span class="synStatement">if</span> (env.IsDevelopment())
{
app.UseDeveloperExceptionPage();
}

<span class="synComment">// もう要らないのでコメントオフ</span>
<span class="synComment">// app.Run(async (context) =&gt;</span>
<span class="synComment">// {</span>
<span class="synComment">//     await context.Response.WriteAsync(&quot;Hello World!&quot;);</span>
<span class="synComment">// });</span>

app.UseMvc();
}
}
}
</pre><p>これだけだと実行して何も表示されないので、ビューも追加しましょう。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20170815041428.png" alt="f:id:daruyanagi:20170815041428p:plain" title="f:id:daruyanagi:20170815041428p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>まず、アプリケーションルートに Pages フォルダーを作成。Razor Pages の *.cshtml はここに保存します（設定で変更可能できるらしいけど）。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20170815035213.png" alt="f:id:daruyanagi:20170815035213p:plain" title="f:id:daruyanagi:20170815035213p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>次に Pages フォルダーのコンテキストメニュー から“MVC ビュー”を追加。これは要するに *.cshtml ファイルです。“Razor ページ”でも *.cshtml を追加できますが、ビューモデルの *.cs ファイルもくっついてくるので（これはこれで便利だけど、まだお子さまには早い！）、今回は“MVC ビュー”にしておきました。</p><p>ちなみに、名前は Index.cshtml にしておきます。<code>/</code> にアクセスすると、<code>/Pages/Index.cshtml</code> が自動で表示される仕組みになっていますので（ルーティングの規則については、また機会を改めましょう）。</p><p>内容はこんな感じ。ごちゃごちゃ書いてあるのは、［Ctrl］＋［A］して［Delete］しちゃって下さい。</p>
<pre class="code lang-html" data-lang="html" data-unlink>@page

<span class="synIdentifier">&lt;</span><span class="synStatement">p</span><span class="synIdentifier">&gt;</span>Hello! World<span class="synIdentifier">&lt;/</span><span class="synStatement">p</span><span class="synIdentifier">&gt;</span>
</pre><p>［F5］キーで実行すると、こんな感じになるはずです。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20170815035710.png" alt="f:id:daruyanagi:20170815035710p:plain" title="f:id:daruyanagi:20170815035710p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>できた＼(＾o＾)／</p><p>でも、これだけでは Razor Pages を使っている意味がないので、変数を使ってみます（文法に関しては説明しません。ググってね！　めっちゃ簡単だよ）。</p>
<pre class="code lang-html" data-lang="html" data-unlink>@page

@{
var message = &quot;Hello! World&quot;;
}

<span class="synIdentifier">&lt;</span><span class="synStatement">p</span><span class="synIdentifier">&gt;</span>@message by Razor Pages<span class="synIdentifier">&lt;/</span><span class="synStatement">p</span><span class="synIdentifier">&gt;</span>
</pre><p>ページの先頭に<i>「Razor Pages だよ！」</i>ってことを知らせるディレクティブ @page を追加している以外は ASP.NET Web Pages（Razor）とまったく変わりません。</p><p>保存してブラウザーをリロードするとこんな感じになるでしょう。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20170815040013.png" alt="f:id:daruyanagi:20170815040013p:plain" title="f:id:daruyanagi:20170815040013p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>あんまり面白くないですかね？　こうしてみますか。</p>
<pre class="code lang-html" data-lang="html" data-unlink>@page &quot;{message?}&quot;

@{
var message = Request.Query[&quot;message&quot;];
}

<span class="synIdentifier">&lt;</span><span class="synStatement">p</span><span class="synIdentifier">&gt;</span>@message by Razor Pages<span class="synIdentifier">&lt;/</span><span class="synStatement">p</span><span class="synIdentifier">&gt;</span>
</pre><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20170815040646.png" alt="f:id:daruyanagi:20170815040646p:plain" title="f:id:daruyanagi:20170815040646p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>@pages のあとに routing constraint を書けるのは新しいかもしれません。この例では正直意味がないのですが（消してもそのまま動くしな）、モデルで <i>void OnGet(string message)</i> などと受け取れるので覚えておくといい感じ。</p>
<pre class="code lang-html" data-lang="html" data-unlink>@page &quot;{message?}&quot;
@using Microsoft.AspNetCore.Mvc.RazorPages
@model IndexModel

@functions
{
public class IndexModel : PageModel
{
public string Message { get; private set; }

public void OnGet(string message)
{
Message = string.IsNullOrEmpty(message)
? &quot;Hello! World&quot;
: message;
}
}
}

<span class="synIdentifier">&lt;</span><span class="synStatement">p</span><span class="synIdentifier">&gt;</span>@Model.Message by Razor Pages<span class="synIdentifier">&lt;/</span><span class="synStatement">p</span><span class="synIdentifier">&gt;</span>
</pre><p>もっと複雑な型データを受け取るときに役立つでしょう。ちなみに @functions の部分は *.cs ファイルに分離することもできます（NEW!）。</p>
<pre class="code lang-html" data-lang="html" data-unlink>@page &quot;{message?}&quot;
@model IndexModel

<span class="synIdentifier">&lt;</span><span class="synStatement">p</span><span class="synIdentifier">&gt;</span>@Model.Message by Razor Pages<span class="synIdentifier">&lt;/</span><span class="synStatement">p</span><span class="synIdentifier">&gt;</span>
</pre><p>ちょうど WPF や WinForm のビュー（デザイナー）＋コードビハインドみたいな感じで、スッキリしていいですね（こういうことがしたい場合は、最初から“MVC ビュー”ではなく“Razor ビュー”を追加するといいです）。</p><p>もっと詳しいことが知りたい場合は、チュートリアルページを参照してください。自分もあとでゆっくり読んでみようと思います。</p><p><iframe src="https://hatenablog-parts.com/embed?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Faspnet%2Fcore%2Fmvc%2Frazor-pages%2F" title="Introduction to Razor Pages in ASP.NET Core" class="embed-card embed-webcard" scrolling="no" frameborder="0" style="display: block; width: 100%; height: 155px; max-width: 500px; margin: 10px 0px;"></iframe><cite class="hatena-citation"><a href="https://docs.microsoft.com/en-us/aspnet/core/mvc/razor-pages/">docs.microsoft.com</a></cite></p><p><iframe src="https://hatenablog-parts.com/embed?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Faspnet%2Fcore%2Ftutorials%2Frazor-pages%2Frazor-pages-start" title="Getting started with Razor Pages in ASP.NET Core" class="embed-card embed-webcard" scrolling="no" frameborder="0" style="display: block; width: 100%; height: 155px; max-width: 500px; margin: 10px 0px;"></iframe><cite class="hatena-citation"><a href="https://docs.microsoft.com/en-us/aspnet/core/tutorials/razor-pages/razor-pages-start">docs.microsoft.com</a></cite><br />
</p>

</div>
<div class="section">
<h3>おまけ</h3>
<p><span itemscope itemtype="http://schema.org/Photograph"><img src="20170815041046.png" alt="f:id:daruyanagi:20170815041046p:plain" title="f:id:daruyanagi:20170815041046p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>空のアプリケーションには 2 つの NuGet パッケージが含まれています。</p>

<ul>
<li>Microsoft.AspNetCore.All</li>
<li>Microsoft.NETCore.App</li>
</ul><p>初期状態ではどっちもプレビュー版で、前者のみ v2.0.0 正式版へのアップデートが提供されています。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20170815041223.png" alt="f:id:daruyanagi:20170815041223p:plain" title="f:id:daruyanagi:20170815041223p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>でも、片っぽだけアップデートすると実行時にコケるみたい。もうちょっと待ちますかね。</p>

</div>