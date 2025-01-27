---
date: 2018-09-08T23:39:48.0000000
draft: false
title: "9月8日：巷もすなる Blazor というものを、おっさんもかいてみんとてするなり"
tags: ["Blazor"]
eyecatch: 
---
<p><span itemscope itemtype="http://schema.org/Photograph"><img src="20180908230602.png" alt="f:id:daruyanagi:20180908230602p:plain" title="f:id:daruyanagi:20180908230602p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>巷もすなる Blazor というものを、おっさんもかいてみんとてするなり。この前のプロ生・大阪で聞いてきた内容を反芻しながらだけど、実際手を動かしてみるといろいろわからんことがでてきた。</p><p><iframe src="https://hatenablog-parts.com/embed?url=https%3A%2F%2Fblog.daruyanagi.jp%2Fentry%2F2018%2F09%2F06%2F004356" title="9月1日：プロ生勉強会 第53回＠GMOインターネット（大阪）に参加してきました（※勉強会の話はあまりない - だるろぐ" class="embed-card embed-blogcard" scrolling="no" frameborder="0" style="display: block; width: 100%; height: 190px; max-width: 500px; margin: 10px 0px;"></iframe><cite class="hatena-citation"><a href="https://blog.daruyanagi.jp/entry/2018/09/06/004356">blog.daruyanagi.jp</a></cite></p><p>ちなみに Blazor というのは Razor（C#）で WebAssembly を作っちまおうぜっていうプロジェクトなのだそうだ。サーバーもクライアントも C# で書けるのがいいと思う（JavaScript は極力やりたくねー！）。</p>

<div class="section">
<h3>@inject HttpClient Http</h3>
<p>DI で注入するとクライアントで HttpClient が使えるようになるんだけど、なんで @using じゃないのかなー……たぶん「HttpClient をクライアントで使うぜー、アセンブリをローカルへダウンロードしてくれー」って言わなきゃいけないからだな。</p>

</div>
<div class="section">
<h3>HtmlString</h3>
<p>エンコード済みの文字列を扱いたかったのだけど、<code>MvcString</code> や <code>HtmlString</code> がなかった。代わりに<code>MarkupString</code>というのがあるので、それを使うといいらしい。</p>
<pre class="code lang-cs" data-lang="cs" data-unlink>@((MarkupString)myMarkup)

@functions {
<span class="synType">string</span> myMarkup = <span class="synConstant">&quot;&lt;p &gt;This is a markup string.&lt;/p&gt;&quot;</span>;
}
</pre><p>詳しくはみんな大好き StackOverFlow を参照。</p><p><iframe src="https://hatenablog-parts.com/embed?url=https%3A%2F%2Fstackoverflow.com%2Fquestions%2F50604366%2Fis-there-an-equivalent-to-html-raw-in-blazor" title="Is there an equivalent to Html.Raw in Blazor?" class="embed-card embed-webcard" scrolling="no" frameborder="0" style="display: block; width: 100%; height: 155px; max-width: 500px; margin: 10px 0px;"></iframe><cite class="hatena-citation"><a href="https://stackoverflow.com/questions/50604366/is-there-an-equivalent-to-html-raw-in-blazor">stackoverflow.com</a></cite></p><p>むしろワークアラウンドの2個目が大事そうな気がする。その先のリンクにある issue でしゃべってる内容がさっぱりわからんが、そこらへんは Blazor の仕組みをもう少し知らないとダメだな。</p>

</div>
<div class="section">
<h3>Loading......</h3>
<p>クライアントに</p>
<pre class="code lang-cs" data-lang="cs" data-unlink>@<span class="synStatement">if</span> (obj == <span class="synConstant">null</span>)
{
&lt;p&gt;Loading...&lt;/p&gt;
}
<span class="synStatement">else</span>
{
&lt;p&gt;@obj.Hoge&lt;/p&gt;
}
</pre><p>などと書くと<code>obj</code>にオブジェクトが格納されるまで「Loading...」と表示されるんだけど、これがなぜかよくわからんかった。で、いろいろこねくり回して気が付いたんだけど、<code>protected override async Task OnInitAsync()</code>で変数を初期化するとビューがリロードされるのかもしれない。変数を複数用意して<code>OnInitAsync()</code>で初期化してみたけど、XHR のときみたいにロードが完了した変数から表示されていくのではなく、すべての読み込みが完了してからページが書き換えられた。そうだとしたら、とくに難しくはない。</p>

</div>
<div class="section">
<h3>ShiftJIS の扱い</h3>
<p>今回は鉄道やフェリーの運行情報をスクレイピングするサイトを作っていたのだけど、1件だけ ShiftJIS なサイトがあった（ガッデム！）。ASP.NET Core の場合、NuGet で<code>System.Text.Encoding.CodePages</code>を追加して</p>
<pre class="code lang-cs" data-lang="cs" data-unlink><span class="synComment">// これがないと下行で例外</span>
Encoding.RegisterProvider(CodePagesEncodingProvider.Instance);
<span class="synComment">// ShiftJIS エンコーディングを取得</span>
var encoding = Encoding.GetEncoding(<span class="synConstant">932</span>);
var reader = <span class="synStatement">new</span> System.IO.StreamReader(stream, encoding);
var text = await reader.ReadToEndAsync());
</pre><p>みたいな感じで処理してあげないといけない。</p>

</div>
<div class="section">
<h3>nuget の構成が無効です。</h3>
<p><blockquote class="twitter-tweet"><p lang="ja" dir="ltr">nuget の構成が無効です。 <a href="https://t.co/4yuTN4BAws">pic.twitter.com/4yuTN4BAws</a></p>&mdash; だるやなぎ准将 (@daruyanagi) <a href="https://twitter.com/daruyanagi/status/1038418815665618945?ref_src=twsrc%5Etfw">September 8, 2018</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> </p><p>一瞬焦ったけど、Visual Studio の再起動で治った。</p>

</div>
<div class="section">
<h3>ビルドが始まらない</h3>
<p>［Ctrl］＋［Break］でビルドを中断し、再度実行するとだいたい成功する。</p>

</div>
<div class="section">
<h3>ビューのコンパイルが面倒</h3>
<p>Razor はビュー部分を編集するとすぐにブラウザーへ反映されたけど、WebAssembly になってるとそうはいかない。ちょろっとした変更でもコンパイルが必要になる。これは割と面倒くさい気がした。</p><p>バインディングやコンポーネントはまだわかってないけど、これは結構楽しいかもしれないなーと思った。Share プロジェクトにモデルを書くと、Server と Client で共有できるのとか、結構うれしい……JSON でシリアライズ・デシリアライズしなくていいしなー（← そこか？）。サーバーサイドは MVC/API の知識が使えるし、クライアントサイドは Razor の経験が役立つ。ここにメリットを感じる人＆なんでも C# で書きたい人にはドンピシャなプロジェクトだと思った。</p><p>ちなみに、今作ってるアプリは愛媛県の交通状況を一覧できるようにしたものだけど</p>

<ul>
<li>飛行機の遅延情報（電車と船はだいたい完了）</li>
<li>キャッシュ機構（スクレイピング元に迷惑がかかる）</li>
<li>通知</li>
</ul><p>を作ったら公開したいかなって思う。いつになるか、モチベが続くかは知らない。</p>

</div>