---
date: 2012-10-31T19:42:22.0000000
draft: false
title: "C# も神だった！　（もちろん、WebMatrix も神）"
tags: ["C#", "WebMatrix"]
eyecatch: 
---

<blockquote cite="http://www.whitehackerz.jp/blog/?p=1154">
<p>0.1を10回足してみた。</p>

<ul>
<li>PHPでの結果、１</li>
<li>JavaScriptでの結果、 0.9999999999999999</li>
<li>Pythonでの結果、0.9999999999999999</li>
<li>Rubyでの結果、1.0</li>
<li>Haskellでの結果0.9999999999999999</li>
</ul><p><b>結論、PHPは神、その次、Ruby</b></p>

<cite><a href="http://www.whitehackerz.jp/blog/?p=1154">0.1&#x3092;10&#x56DE;&#x8DB3;&#x3057;&#x3066;&#x307F;&#x305F;&#x7D50;&#x679C;PHP&#x304C;&#x795E;&#x3068;&#x8A00;&#x3046;&#x4E8B;&#x304C;&#x5224;&#x660E;&#x3057;&#x307E;&#x3057;&#x305F; | WhiteHackerzBlog &#x30CF;&#x30C3;&#x30AB;&#x30FC;&#x990A;&#x6210;&#x5B66;&#x9662; &#x516C;&#x5F0F;&#x30D6;&#x30ED;&#x30B0;</a></cite>
</blockquote>
<p>何がいいたいのかよくわかんないのだけど、とりあえず C# で試してみた。</p>
<pre class="code lang-cs" data-lang="cs" data-unlink><span class="synStatement">using</span> System;
<span class="synStatement">using</span> System.Collections.Generic;
<span class="synStatement">using</span> System.Linq;
<span class="synStatement">using</span> System.Text;
<span class="synStatement">using</span> System.Threading.Tasks;

<span class="synType">namespace</span> ConsoleApplication1
{
<span class="synType">class</span> Program
{
<span class="synType">static</span> <span class="synType">void</span> Main(<span class="synType">string</span>[] args)
{
Console.WriteLine(<span class="synConstant">0.1</span> + <span class="synConstant">0.1</span> + <span class="synConstant">0.1</span> + <span class="synConstant">0.1</span> + <span class="synConstant">0.1</span> + <span class="synConstant">0.1</span> + <span class="synConstant">0.1</span> + <span class="synConstant">0.1</span> + <span class="synConstant">0.1</span> + <span class="synConstant">0.1</span>);
Console.ReadKey();
}
}
}
</pre><p><img src="20121031193448.png" alt="f:id:daruyanagi:20121031193448p:plain" title="f:id:daruyanagi:20121031193448p:plain" class="hatena-fotolife"></p><p>結論、<b>C# も神</b>。</p>

<div class="section">
<h3>おまけ</h3>
<p><img src="20121031193649.png" alt="f:id:daruyanagi:20121031193649p:plain" title="f:id:daruyanagi:20121031193649p:plain" class="hatena-fotolife"><img src="20121031193833.png" alt="f:id:daruyanagi:20121031193833p:plain" title="f:id:daruyanagi:20121031193833p:plain" class="hatena-fotolife"></p><p>もちろん、<b>WebMatrix も神</b>だ。</p>

</div>
<div class="section">
<h3>おまけ2</h3>
<p>個人的には Ruby が一番偉い気がする。</p>

</div>
<div class="section">
<h3>おまけ3</h3>
<p>1 = 0.9999999999999999…</p><p>で合ってるよね？　わしは文系だからよくわかんないけど。</p>

</div>
<div class="section">
<h3>おまけ4</h3>
<pre class="code lang-cs" data-lang="cs" data-unlink><span class="synStatement">using</span> System;
<span class="synStatement">using</span> System.Collections.Generic;
<span class="synStatement">using</span> System.Linq;
<span class="synStatement">using</span> System.Text;
<span class="synStatement">using</span> System.Threading.Tasks;

<span class="synType">namespace</span> ConsoleApplication1
{
<span class="synType">class</span> Program
{
<span class="synType">static</span> <span class="synType">void</span> Main(<span class="synType">string</span>[] args)
{
Console.WriteLine(
<span class="synConstant">&quot;{0:0.0}&quot;</span>,
<span class="synConstant">0.1</span> + <span class="synConstant">0.1</span> + <span class="synConstant">0.1</span> + <span class="synConstant">0.1</span> + <span class="synConstant">0.1</span> + <span class="synConstant">0.1</span> + <span class="synConstant">0.1</span> + <span class="synConstant">0.1</span> + <span class="synConstant">0.1</span> + <span class="synConstant">0.1</span>);
Console.ReadKey();
}
}
}
</pre><p>これだと 1.0 と出力されるのがご存じのとおり。</p>

</div>
<div class="section">
<h3>追記</h3>
<p><div class="twitter-detail twitter-detail-left"><div class="twitter-detail-user"><a class="twitter-user-screen-name" href="http://twitter.com/ufcpp"><img src="http://a0.twimg.com/profile_images/1221325140/10da2e99-7336-48a0-afe5-baaa6dc6578b_normal.png" alt="ufcpp" height="48" width="48"></a></div><div class="twitter-detail-tweet"><p class="twitter-detail-text"><a class="twitter-tweet-url" href="http://t.co/wXwi7aGS" target="_top"><span>URL</span></a> これ、表示の際に丸目てるか切り捨ててるかだけの差のはず。C# も0.1を10回足したらバイナリ的には 3FEFFFFFFFFFFFFF。浮動小数点数の仕様。decimal使わないと。</p><p class="twitter-detail-info"><a href="http://twitter.com/ufcpp/status/263618107703193601" class="twitter-detail-info-permalink"><span class="twitter-detail-info-date">2012-10-31</span> <span class="twitter-detail-info-time">21:27:09</span></a> <span class="twitter-detail-info-source">via <a href="http://www.s-software.net/" rel="nofollow">みについ</a></span></p></div></div></p><p>もともと内部表現ではなく出力に着目するのががおかしいなぁ、という問題意識でこのエントリーは書いたので「C# が神！」というのはほとんど冗談なのだけど、decimal じゃないとダメというくだりは気になったので試してみた。</p>
<pre class="code lang-cs" data-lang="cs" data-unlink><span class="synStatement">using</span> System;
<span class="synStatement">using</span> System.Collections.Generic;
<span class="synStatement">using</span> System.Linq;
<span class="synStatement">using</span> System.Text;
<span class="synStatement">using</span> System.Threading.Tasks;

<span class="synType">namespace</span> ConsoleApplication1
{
<span class="synType">class</span> Program
{
<span class="synType">static</span> <span class="synType">void</span> Main(<span class="synType">string</span>[] args)
{
Console.WriteLine((<span class="synType">decimal</span>)(<span class="synConstant">0.1</span> + <span class="synConstant">0.1</span> + <span class="synConstant">0.1</span> + <span class="synConstant">0.1</span> + <span class="synConstant">0.1</span> + <span class="synConstant">0.1</span> + <span class="synConstant">0.1</span> + <span class="synConstant">0.1</span> + <span class="synConstant">0.1</span> + <span class="synConstant">0.1</span>));
Console.ReadKey();
}
}
}
</pre><p><img src="20121031213411.png" alt="f:id:daruyanagi:20121031213411p:plain" title="f:id:daruyanagi:20121031213411p:plain" class="hatena-fotolife"></p><p>ちゃんと 1.0 になった（＠＠；</p><p>decimal でキャストせずに 1.0m <a href="#f1" name="fn1" title="m は decimal として扱うためのサフィックス">*1</a>を足した場合でも、結果は一緒だった。</p>

</div><div class="footnote">
<p class="footnote"><a href="#fn1" name="f1" class="footnote-number">*1</a><span class="footnote-delimiter">:</span><span class="footnote-text">m は decimal として扱うためのサフィックス</span></p>
</div>