---
date: 2013-12-11T01:58:27.0000000
draft: false
title: "ASP.NET Web Pages: より柔軟なルーティングを利用する"
tags: ["ASP.net Web Pages", "WebMatrix"]
eyecatch: http://cdn-ak.f.st-hatena.com/images/fotolife/d/daruyanagi/20131205/20131205024503.png
---
<p><span itemscope itemtype="http://schema.org/Photograph"><img src="20131205024503.png" alt="f:id:daruyanagi:20131205024503p:plain" title="f:id:daruyanagi:20131205024503p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>※ この記事は <a href="http://www.adventar.org/calendars/132">One ASP.NET Advent Calendar 2013</a> の11日目の記事です。<a href="http://blogonos.wordpress.com/2013/12/10/asp-net-identity-%E3%83%97%E3%83%AD%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%81%AE%E8%BF%BD%E5%8A%A0/">@ono &#x3055;&#x3093;</a>、ありがとうございます！</p>

<blockquote cite="http://www.infoq.com/jp/articles/Microsoft-Stack-2013">
<p>ASP.NET Web Pagesは4番目の選択肢です。Razorのシンタックスのおかげで、PHPやクラシックASPに似た開発経験を提供してくれます。</p>

<cite><a href="http://www.infoq.com/jp/articles/Microsoft-Stack-2013">Microsoft&#x306E;&#x6280;&#x8853;&#x306E;&#x6D3B;&#x7528;&#x65B9;&#x6CD5;</a></cite>
</blockquote>
<p>どうも恐縮です！　“4番目の選択肢”が大好きな @daruyanagi です。ウェブベースのアプリを作るとき、ASP.NET Web Pages は LightSwitch の次にお勧めデス。とくに動的な“ペライチ”<a href="#f-5fab35cf" name="fn-5fab35cf" title="あんまりこの言葉って使われないらしいですね？　ペラペラの紙一枚って感じの意味です">*1</a>のサイトを作るにはピッタリで、MVC とか API とか Single Page Application とかわかんない僕でも少しはわかるぐらいの簡単さ。これから広大な One ASP.NET の海に漕ぎ出そうという入門者にはピッタリの技術なのではないかと思います。とくに年頃の娘さんにはお勧めしたいですね！</p><p>――ま、そんなことは置いておいて。</p><p>今日は ASP.NET Web Pages におけるルーティングの話です。“ペライチ”のサイトを作るには実はあまり関係ないのですけど、データベースを扱うページを作る場合、知っておくと URL がカッコいいサイトが作れるのではないでしょうか。SEO にもいいらしいです。知らんけど。</p>

<div class="section">
<h3>規約ベースのルーティング</h3>
<p>勝手にそう呼んでみましたが、ASP.NET Web Pages で一番簡単かつ基礎となるルーティングです。</p><p>ASP.NET Web Pages は <i>/Default/あ/い/う/え/お </i>というリソースへのリクエストを受け取ると、<i>~/Default/あ/い/う/え/お.cshtml </i>を探しに行きます。なければ <i>~/Default/あ/い/う/え.cshtml</i> を、次は <i>~/Default/あ/い/う.cshtml</i> を……。そしてついにこんな <b>~/Default.cshtml</b> を発見します。</p>
<pre class="code lang-html" data-lang="html" data-unlink><span class="synComment">&lt;!-- ~/Default.cshtml --&gt;</span>

<span class="synComment">&lt;!DOCTYPE html&gt;</span>

<span class="synIdentifier">&lt;</span><span class="synStatement">html</span><span class="synIdentifier"> </span><span class="synType">lang</span><span class="synIdentifier">=</span><span class="synConstant">&quot;ja&quot;</span><span class="synIdentifier">&gt;</span>
<span class="synIdentifier">&lt;</span><span class="synStatement">head</span><span class="synIdentifier">&gt;</span>
<span class="synPreProc">        </span><span class="synIdentifier">&lt;</span><span class="synStatement">meta</span><span class="synIdentifier"> </span><span class="synType">charset</span><span class="synIdentifier">=</span><span class="synConstant">&quot;utf-8&quot;</span><span class="synIdentifier"> /&gt;</span>
<span class="synPreProc">        </span><span class="synIdentifier">&lt;</span><span class="synStatement">title</span><span class="synIdentifier">&gt;</span>マイ サイトのタイトル<span class="synIdentifier">&lt;/</span><span class="synStatement">title</span><span class="synIdentifier">&gt;</span>
<span class="synPreProc">        </span><span class="synIdentifier">&lt;</span><span class="synStatement">link</span><span class="synIdentifier"> </span><span class="synType">href</span><span class="synIdentifier">=</span><span class="synConstant">&quot;~/favicon.ico&quot;</span><span class="synIdentifier"> </span><span class="synType">rel</span><span class="synIdentifier">=</span><span class="synConstant">&quot;shortcut icon&quot;</span><span class="synIdentifier"> </span><span class="synType">type</span><span class="synIdentifier">=</span><span class="synConstant">&quot;image/x-icon&quot;</span><span class="synIdentifier"> /&gt;</span>
<span class="synPreProc">    </span><span class="synIdentifier">&lt;/</span><span class="synStatement">head</span><span class="synIdentifier">&gt;</span>
<span class="synIdentifier">&lt;</span><span class="synStatement">body</span><span class="synIdentifier">&gt;</span>
<span class="synIdentifier">&lt;</span><span class="synStatement">ul</span><span class="synIdentifier">&gt;</span>
@foreach (var data in UrlData)
{
<span class="synIdentifier">&lt;</span><span class="synStatement">li</span><span class="synIdentifier">&gt;</span>@data<span class="synIdentifier">&lt;/</span><span class="synStatement">li</span><span class="synIdentifier">&gt;</span>
}
<span class="synIdentifier">&lt;/</span><span class="synStatement">ul</span><span class="synIdentifier">&gt;</span>
<span class="synIdentifier">&lt;/</span><span class="synStatement">body</span><span class="synIdentifier">&gt;</span>
<span class="synIdentifier">&lt;/</span><span class="synStatement">html</span><span class="synIdentifier">&gt;</span>
</pre><p>後ろにくっついていた <b>あ/い/う/え/お</b> は“/”で区切られ、<a href="http://msdn.microsoft.com/query/dev12.query?appId=Dev12IDEF1&l=JA-JP&k=k(System.Web.WebPages.WebPageRenderingBase.UrlData);k(TargetFrameworkMoniker-.NETFramework,Version%3Dv4.0);k(DevLang-csharp)&rd=true">UrlData</a> に配列（IList<string>）として格納されます。なので、この ~/Defailt.cshtml の出力はこんな感じになります。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20131205033505.png" alt="f:id:daruyanagi:20131205033505p:plain" title="f:id:daruyanagi:20131205033505p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>これを利用すれば、/Wiki/?title=だるやなぎ ではなく /Wiki/だるやなぎ だったり、/Product/?name=綾鷹&count=10 ではなく /Product/綾鷹/10 という URL を設計できると思います。ただし、ちょっとユルユルな感じはしますね。綾鷹の例で言えば、UrlData[0] = name / UrlData[1] = count というバインディング（紐づけ）を自分で管理しなければならない。設計が変わって、新しいパラメーターが追加されたときやパラメーターの順番が入れ替わったとき、刻の涙をみる羽目に陥るかも。</p><p>そのほかにも、ASP.NET Web Pages はいろいろなルーティング規約（？）があって、知っておくと割といろいろなことができます。もし興味があれば、この記事を参照してください（ちょっと古いし間違ってるかもだけど）。</p>

<ul>
<li><a href="https://blog.daruyanagi.jp/entry/2012/07/06/174414">WebMatrix &#x306E;&#x30EB;&#x30FC;&#x30C6;&#x30A3;&#x30F3;&#x30B0; - &#x3060;&#x308B;&#x308D;&#x3050;</a></li>
</ul>
</div>
<div class="section">
<h3>URL リライト</h3>
<p>IIS 7.0 以降であれば URL リライトモジュールを利用してもいいと思います。</p><p>たとえば、</p>
<pre class="code" data-lang="" data-unlink>http://sample.com/Pages.cshtml/Hoge
http://sample.com/Pages/Hoge</pre><p>を</p>
<pre class="code" data-lang="" data-unlink>http://sample.com/Hoge</pre><p>に飛ばしたい場合、Web.config を以下のように編集します。</p>
<pre class="code lang-xml" data-lang="xml" data-unlink><span class="synComment">&lt;?</span><span class="synType">xml version</span>=<span class="synConstant">&quot;1.0&quot;</span><span class="synComment">?&gt;</span>
<span class="synIdentifier">&lt;configuration&gt;</span>
<span class="synIdentifier">&lt;system</span><span class="synComment">.</span><span class="synIdentifier">webServer&gt;</span>
<span class="synIdentifier">&lt;rewrite&gt;</span>
<span class="synIdentifier">&lt;rules&gt;</span>
<span class="synIdentifier">&lt;rule </span><span class="synType">name</span>=<span class="synConstant">&quot;Daruboard&quot;</span><span class="synIdentifier"> </span><span class="synType">stopProcessing</span>=<span class="synConstant">&quot;true&quot;</span><span class="synIdentifier">&gt;</span>
<span class="synIdentifier">&lt;match </span><span class="synType">url</span>=<span class="synConstant">&quot;^(.*)$&quot;</span><span class="synIdentifier"> </span><span class="synType">ignoreCase</span>=<span class="synConstant">&quot;false&quot;</span><span class="synIdentifier"> /&gt;</span>
<span class="synIdentifier">&lt;conditions&gt;</span>
<span class="synIdentifier">&lt;add </span><span class="synType">input</span>=<span class="synConstant">&quot;{REQUEST_FILENAME}&quot;</span><span class="synIdentifier"> </span><span class="synType">matchType</span>=<span class="synConstant">&quot;IsFile&quot;</span><span class="synIdentifier"> </span><span class="synType">ignoreCase</span>=<span class="synConstant">&quot;false&quot;</span><span class="synIdentifier"> </span><span class="synType">negate</span>=<span class="synConstant">&quot;true&quot;</span><span class="synIdentifier"> /&gt;</span>
<span class="synIdentifier">&lt;add </span><span class="synType">input</span>=<span class="synConstant">&quot;{REQUEST_FILENAME}&quot;</span><span class="synIdentifier"> </span><span class="synType">matchType</span>=<span class="synConstant">&quot;IsDirectory&quot;</span><span class="synIdentifier"> </span><span class="synType">ignoreCase</span>=<span class="synConstant">&quot;false&quot;</span><span class="synIdentifier"> </span><span class="synType">negate</span>=<span class="synConstant">&quot;true&quot;</span><span class="synIdentifier"> /&gt;</span>
<span class="synIdentifier">&lt;/conditions&gt;</span>
<span class="synIdentifier">&lt;action </span><span class="synType">type</span>=<span class="synConstant">&quot;Rewrite&quot;</span><span class="synIdentifier"> </span><span class="synType">url</span>=<span class="synConstant">&quot;Pages.cshtml/{R:1}&quot;</span><span class="synIdentifier"> /&gt;</span>
<span class="synIdentifier">&lt;/rule&gt;</span>
<span class="synIdentifier">&lt;/rules&gt;</span>
<span class="synIdentifier">&lt;/rewrite&gt;</span>
<span class="synIdentifier">&lt;/system</span><span class="synComment">.</span><span class="synIdentifier">webServer&gt;</span>
<span class="synIdentifier">&lt;/configuration&gt;</span>
</pre><p>このやり方は割かし強力で、規範ベースのルーティングの例で言えば /Default すら消すことができます（先のやり方では、既定のページに Default.cshtml を加えていたとしても、 /Default/あ/い/う/え/お の /Default が省略できません）。</p><p>ただ、個人的にはあんまりやりたくないです。IIS ベッタリだし、書き方もよくわからん（ぉ</p>

</div>
<div class="section">
<h3>IRouteHandler を実装する</h3>
<p>ASP.NET Web Pages は ASP.NET ファミリーの一員ですので、ASP.NET の作法が使えます。つまり、<a href="http://msdn.microsoft.com/ja-jp/library/system.web.routing.iroutehandler(v=vs.100).aspx">IRouteHandler</a> を実装してルーティングを定義することもできる。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20131205041246.png" alt="f:id:daruyanagi:20131205041246p:plain" title="f:id:daruyanagi:20131205041246p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>ただ、自分で IRouteHandler を実装するのはちょっとめんどくさいので、今回は <a href="http://www.nuget.org/packages/WebPageRouteHandler/">Routing for WebPages</a> を使わせてもらおうと思います。この NuGet には</p>

<ul>
<li>WebPagesRouteHandler：IRouteHandler の実装</li>
<li>MapWebPageRoute 拡張メソッド</li>
<li>GetRouteValue 拡張メソッド</li>
</ul><p>が含まれています。使い方は――</p>
<pre class="code lang-cs" data-lang="cs" data-unlink><span class="synComment">// ~/_AppStart.cshtml: アプリケーションの起動時に実行されます</span>

@<span class="synStatement">using</span> System.Web.Routing

@{
RouteTable.Routes.MapWebPageRoute(
<span class="synConstant">&quot;List/&quot;</span>,
<span class="synConstant">&quot;~/ListProducts.cshtml&quot;</span>
);
}
</pre><p>まず、MapWebPageRoute を使って ~/_AppStart.cshtml でルーティングを追加。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20131205042059.png" alt="f:id:daruyanagi:20131205042059p:plain" title="f:id:daruyanagi:20131205042059p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>次にこんな ~/ListProducts.cshtml を用意して実行すると――</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20131205042115.png" alt="f:id:daruyanagi:20131205042115p:plain" title="f:id:daruyanagi:20131205042115p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>結果はこんな感じ。~/List.cshtml ではなく ~/ListProducts.cshtml が参照されます。さらに、</p>
<pre class="code lang-cs" data-lang="cs" data-unlink><span class="synComment">// ~/_AppStart.cshtml</span>

@<span class="synStatement">using</span> System.Web.Routing

@{
RouteTable.Routes.MapWebPageRoute(
<span class="synConstant">&quot;List/{category}/&quot;</span>,
<span class="synConstant">&quot;~/ListProducts.cshtml&quot;</span>
);
}
</pre><p>こんな風にすれば――</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20131205042542.png" alt="f:id:daruyanagi:20131205042542p:plain" title="f:id:daruyanagi:20131205042542p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>GetRouteValue で category が取得できる。</p>
<pre class="code lang-cs" data-lang="cs" data-unlink>@{
var category = Context.GetRouteValue(<span class="synConstant">&quot;category&quot;</span>);
}
</pre><p>UrlData では不完全だったバインディングの問題が解決されるのがポイントかな。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20131205044708.png" alt="f:id:daruyanagi:20131205044708p:plain" title="f:id:daruyanagi:20131205044708p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>このルーティングでは category を指定せず /List/ へアクセスすると 404 になるけど――</p>
<pre class="code lang-cs" data-lang="cs" data-unlink><span class="synComment">// ~/_AppStart.cshtml</span>

@<span class="synStatement">using</span> System.Web.Routing

@{
RouteTable.Routes.MapWebPageRoute(
<span class="synConstant">&quot;List/{*category}/&quot;</span>,
<span class="synConstant">&quot;~/ListProducts.cshtml&quot;</span>
);
}
</pre><p>“*”をつけてやれば category がない場合でもマッチする。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20131205044047.png" alt="f:id:daruyanagi:20131205044047p:plain" title="f:id:daruyanagi:20131205044047p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>category に初期値を与えることも。</p>
<pre class="code lang-cs" data-lang="cs" data-unlink><span class="synComment">// ~/_AppStart.cshtml</span>

@<span class="synStatement">using</span> System.Web.Routing

@{
RouteTable.Routes.MapWebPageRoute(
<span class="synConstant">&quot;List/{*category}&quot;</span>,
<span class="synConstant">&quot;~/ListProducts.cshtml&quot;</span>,
<span class="synStatement">new</span> { category = <span class="synConstant">&quot;Beverages&quot;</span> }
);
}
</pre><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20131205044132.png" alt="f:id:daruyanagi:20131205044132p:plain" title="f:id:daruyanagi:20131205044132p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>category に正規表現で制約を設けてみる。</p>
<pre class="code lang-cs" data-lang="cs" data-unlink><span class="synComment">// ~/_AppStart.cshtml</span>

@<span class="synStatement">using</span> System.Web.Routing

@{
RouteTable.Routes.MapWebPageRoute(
<span class="synConstant">&quot;List/{category}&quot;</span>,
<span class="synConstant">&quot;~/ListProducts.cshtml&quot;</span>,
<span class="synStatement">        defaultValues:</span> <span class="synStatement">new</span> { category = <span class="synConstant">&quot;Beverages&quot;</span> },
<span class="synStatement">        constraints:</span> <span class="synStatement">new</span> { category = <span class="synConstant">&quot;[a-zA-Z]+&quot;</span> }
);
}
</pre><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20131205044344.png" alt="f:id:daruyanagi:20131205044344p:plain" title="f:id:daruyanagi:20131205044344p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>/List/Tea は受け付けるが……</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20131205044451.png" alt="f:id:daruyanagi:20131205044451p:plain" title="f:id:daruyanagi:20131205044451p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>/List/お茶 は受け付けない。/Blog/2013/01/01 -> /Blog/{Year}/{Month}/{Day} なんて URL を設計するとき、{Year} {Month} {Day} を数字に限定したいですよね！　そんな時にはこれが使えそう。</p>

</div>
<div class="section">
<h3>まとめ</h3>
<p>今回は ASP.NET Web Pages で使えるルーティング方法を3つ紹介しました。</p>

<table>
<tr>
<td></td>
<td>処理レイヤー</td>
<td>特徴</td>
</tr>
<tr>
<td>URL Rewrite</td>
<td>IIS（Web サーバー）</td>
<td>強力！　だけど面倒で IIS べったりなのが気になる</td>
</tr>
<tr>
<td>IRouteHandler</td>
<td>ASP.NET</td>
<td>中間。バランスはいいかな。NuGet で楽ができる</td>
</tr>
<tr>
<td>規約ベース（UrlData）</td>
<td>ASP.NET Web Pages</td>
<td>とにかくお手軽！　だけどユルユル？</td>
</tr>
</table><p>今回紹介はしなかったけれど、<a href="https://blog.daruyanagi.jp/entry/2013/05/10/085706">NancyFx</a> を使ってみてもいいかもしれない。ページではなく API を実装したい場合には使えそうですよ。</p><p>MVC や Web API もいいけれど、そういう大きなフレームワークに頼るのではなく、手のひらの上でちょっとしたウェブアプリを動かしたいときは ASP.NET Web Pages のことも思い出してもらえるとうれしいです。あと、女子高生のユーザーが増えるといいな。</p><p>次は北陸のイケメン MVP こと <a href="http://xin9le.net/">@xin9le &#x3055;&#x3093;</a>です。よろしく！</p>

<div class="section">
<h4>参照</h4>

<ul>
<li><a href="http://www.thecodingguys.net/tutorials/asp/webpages-routing">ASP.NET Web Pages - Routing | the coding guys</a></li>
<li><a href="http://www.mikesdotnetting.com/Article/187/More-Flexible-Routing-For-ASP.NET-Web-Pages">http://www.mikesdotnetting.com/Article/187/More-Flexible-Routing-For-ASP.NET-Web-Pages</a>（サーバー落ちてるかも）</li>
</ul>
</div>
<div class="section">
<h4>追記</h4>
<p><span itemscope itemtype="http://schema.org/Photograph"><img src="20131211020715.png" alt="f:id:daruyanagi:20131211020715p:plain" title="f:id:daruyanagi:20131211020715p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>縄神さまの周りだけ、Advent Calendar が埋まっていません！　どなたかご協力をお願いします！！</p>

</div>
</div><div class="footnote">
<p class="footnote"><a href="#fn-5fab35cf" name="f-5fab35cf" class="footnote-number">*1</a><span class="footnote-delimiter">:</span><span class="footnote-text">あんまりこの言葉って使われないらしいですね？　ペラペラの紙一枚って感じの意味です</span></p>
</div>