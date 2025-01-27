---
date: 2013-11-12T07:31:04.0000000
draft: false
title: "Windows 7 の Internet Explorer 11 と Windows 8.1 の Internet Explorer 11 の違い"
tags: ["Windows 7", "Windows 8.1", "Internet Explorer"]
eyecatch: 20131110144736.png
---
<p><span itemscope itemtype="http://schema.org/Photograph"><img src="20131110144736.png" alt="f:id:daruyanagi:20131110144736p:plain" title="f:id:daruyanagi:20131110144736p:plain" class="hatena-fotolife" itemprop="image"></span><br />
</p>

<blockquote cite="http://www.forest.impress.co.jp/docs/news/20131108_622701.html">
<p>米Microsoft Corporationは7日（現地時間）、Windows 7向けの「Internet Explorer 11」を正式公開した。現在、日本語版を含む95カ国語版が同社のWebサイトから無償でダウンロード可能。また、“Windows Update”を通じた自動更新も本日より開始される。自動更新の配信はRelease Preview版「Internet Explorer 11」のユーザーから順に行われ、一般ユーザーにも数週間以内に届けられる見込み。</p>

<cite><a href="http://www.forest.impress.co.jp/docs/news/20131108_622701.html">Microsoft&#x3001;Windows 7&#x5411;&#x3051;&#x300C;Internet Explorer 11&#x300D;&#x3092;&#x6B63;&#x5F0F;&#x30EA;&#x30EA;&#x30FC;&#x30B9; - &#x7A93;&#x306E;&#x675C;</a></cite>
</blockquote>
<p>Windows 7 の Internet Explorer 11 は、Windows 8.1 のデスクトップ向け Internet Explorer 11 とほぼ同等の機能をもつのだけれど、完全に同じというわけではない。</p>

<blockquote cite="http://jp.techcrunch.com/2013/11/08/20131107internet-explorer-11-launches-on-windows-7/">
<p>Windows 8.1のユーザが使っているのと基本的に同じブラウザであり、唯一の違いはGoogleのSPDYプロトコルをサポートしていないこと。それ以外では、8.1用と同じスピードの向上、セキュリティとプライバシーのアップデート、WebGLのサポート、インタフェイスのアップデートなどが盛り込まれている。</p>

<cite><a href="http://jp.techcrunch.com/2013/11/08/20131107internet-explorer-11-launches-on-windows-7/">Internet Explorer 11&#x304C;Windows 7&#x306B;&#x3082;&#x3084;&#x3063;&#x3066;&#x304D;&#x305F;: &#x30BB;&#x30AD;&#x30E5;&#x30EA;&#x30C6;&#x30A3;&#x3067;Chrome&#x7B49;&#x306B;&#x5927;&#x5DEE;! | TechCrunch Japan</a></cite>
</blockquote>
<p>この記述はだいぶ怪しくて、SPDY をサポートしていないのは正しいのだけど、それだけが唯一の違いというわけではない。</p><p>細かい内容については、以下のページが詳しい。</p>

<blockquote cite="http://msdn.microsoft.com/ja-jp/library/ie/dn394063(v=vs.85).aspx">
<p>Windows 8.1 での Internet Explorer 11 と Windows 7 での Internet Explorer 11 との間には、HTML5 ビデオ、タッチ サポート、デバイスと画面の向きに関する API、Windows の統合、パフォーマンスの面でいくつかの違いがあります。</p>

<cite><a href="http://msdn.microsoft.com/ja-jp/library/ie/dn394063(v=vs.85).aspx">Windows 7 &#x3067;&#x306E; IE11 (Windows)</a></cite>
</blockquote>
<p>順にみていこう。</p>


<div class="section">
<h3>HTML5 ビデオ</h3>
<p>Windows 7 の Internet Explorer 11 では、<b>Encrypted Media Extensions (EME)</b> と <b>Media Source Extensions (MSE)</b> がサポートされない。</p>

<blockquote cite="http://msdn.microsoft.com/ja-jp/library/ie/bg182646(v=vs.85).aspx">

<div class="section">
<h5>Encrypted Media Extensions (EME)</h5>
<p>EME は video 要素と audio 要素を拡張し、プラグインを使うことなく、デジタル著作権管理 (DRM) で保護されたコンテンツを有効にします。 EME は、Windows 8.1 の Internet Explorer 11 および JavaScript を使っている Windows ストア アプリでサポートされます。</p>

</div>
<div class="section">
<h5>Media Source Extensions (MSE)</h5>
<p>Internet Explorer 11 では、HTML5 の Media Source Extensions (MSE) を使った MPEG-DASH メディア ストリーミングのサポートが導入されています。MSE は、プラグインを使わずにメディア ストリームを動的に変更できる video 要素や audio 要素を拡張します。これにより、アダプティブ メディア ストリーミング、ライブ ストリーミング、ビデオのスプライス、ビデオ編集などの処理ができるようになります。</p>

</div>
<cite><a href="http://msdn.microsoft.com/ja-jp/library/ie/bg182646(v=vs.85).aspx">&#x30D3;&#x30C7;&#x30AA; (Windows)</a></cite>
</blockquote>
<p>EME は HTML5 ビデオでお金儲けをしようと思えば必須の機能になるんだろうね。MSE は回線品質に合わせて JavaScript で動的にビットレートを調整したりできるようにするものみたい。</p><p>ただ、名前に“Extensions”とあるように、ブラウザー側はインターフェイスだけを用意して、実際の処理は外部モジュールに丸投げする形式になっているようで、断片化を懸念する声もあるみたい。いろんな形式が乱立しちゃって、結局使い勝手が悪いみたいなことにならなければいいけど。</p>

</div>
<div class="section">
<h3>Windows 8.1 統合</h3>
<p>Windows 7 の Internet Explorer 11 は Windows 8.x で追加された機能にアクセスできない。 </p><p>たとえばリモート端末のタブアクセスや、強化されたライブタイルなんかがそれ。サイトのピン止めでライブタイルにできるのは、自分のサイトでも今度試してみたいな。</p>

<ul>
<li><a href="http://msdn.microsoft.com/ja-jp/library/ie/dn265048(v=vs.85).aspx">Windows &#x7D71;&#x5408; (Windows)</a></li>
<li><a href="http://msdn.microsoft.com/ja-jp/library/ie/bg183312(v=vs.85).aspx">&#x30D4;&#x30F3;&#x7559;&#x3081;&#x3055;&#x308C;&#x305F;&#x30B5;&#x30A4;&#x30C8;&#x306E;&#x6A5F;&#x80FD;&#x5F37;&#x5316; (Windows)</a></li>
<li><a href="http://msdn.microsoft.com/ja-jp/library/ie/dn265018(v=vs.85).aspx">&#x96FB;&#x8A71;&#x756A;&#x53F7;&#x306E;&#x5F62;&#x5F0F;&#x306E;&#x8A8D;&#x8B58; (Windows)</a></li>
</ul><p>電話番号の認識は、Skype との連携なんかに使われている。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20131112071024.jpg" alt="f:id:daruyanagi:20131112071024j:plain" title="f:id:daruyanagi:20131112071024j:plain" class="hatena-fotolife" itemprop="image"></span><br />
</p>

<ul>
<li><a href="http://www.forest.impress.co.jp/docs/news/20131023_620660.html">&#x300C;Windows 8.1&#x300D;&#x306B;&#x3074;&#x3063;&#x305F;&#x308A;&#x306E;&#x300C;Skype&#x300D;&#x3001;&#x300C;Skype for Windows 8.1&#x300D;&#x304C;&#x6B63;&#x5F0F;&#x306B;&#x30EA;&#x30EA;&#x30FC;&#x30B9; - &#x7A93;&#x306E;&#x675C;</a></li>
</ul>
</div>
<div class="section">
<h3>いまどきのタブレット対応</h3>
<p>Windows 7 と Windows 8.x の違いとして、タブレット対応が挙げられる。もちろん、Windows 8.1 でしかサポートされていない機能は、Windows 7 の Internet Explorer 11 には搭載されていない。</p>

<div class="section">
<h4>タッチ サポート</h4>
<p><span itemscope itemtype="http://schema.org/Photograph"><img src="20131112072153.png" alt="f:id:daruyanagi:20131112072153p:plain" title="f:id:daruyanagi:20131112072153p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>タッチサポートといっても単に触れるってだけじゃなくて、タッチならではの問題に取り組んだり、マウスオペレーションでしかアクセスできない機能を潰したりと、なかなか難しいっぽい。</p>

<ul>
<li><a href="http://msdn.microsoft.com/ja-jp/library/ie/dn265022(v=vs.85).aspx">&#x30C9;&#x30E9;&#x30C3;&#x30B0; &#x30A2;&#x30F3;&#x30C9; &#x30C9;&#x30ED;&#x30C3;&#x30D7; &#x30BF;&#x30C3;&#x30C1; &#x30B5;&#x30DD;&#x30FC;&#x30C8; (Windows)</a></li>
<li><a href="http://msdn.microsoft.com/ja-jp/library/ie/dn265041(v=vs.85).aspx">&#x30BF;&#x30C3;&#x30C1;&#x5165;&#x529B;&#x3084;&#x305D;&#x306E;&#x4ED6;&#x306E;&#x5165;&#x529B;&#x306B;&#x3088;&#x308B;&#x30B9;&#x30AF;&#x30ED;&#x30FC;&#x30EB;&#x3068;&#x30BA;&#x30FC;&#x30E0; (Windows)</a></li>
<li><a href="http://msdn.microsoft.com/ja-jp/library/ie/dn265029(v=vs.85).aspx">&#x30DB;&#x30D0;&#x30FC; &#x30BF;&#x30C3;&#x30C1; &#x30B5;&#x30DD;&#x30FC;&#x30C8; (Windows)</a></li>
</ul><p>タブレット使うなら Windows 8.1 ってことやな。</p>

<ul>
<li><a href="http://blogs.msdn.com/b/ie_ja/archive/2013/08/06/ie11-touch-browsing-for-todays-web-and-beyond.aspx">IE11: &#x73FE;&#x5728;&#x305D;&#x3057;&#x3066;&#x5C06;&#x6765;&#x306E; Web &#x306B;&#x5BFE;&#x5FDC;&#x3059;&#x308B;&#x30BF;&#x30C3;&#x30C1; &#x30D6;&#x30E9;&#x30A6;&#x30B8;&#x30F3;&#x30B0; - IEBlog &#x65E5;&#x672C;&#x8A9E; - Site Home - MSDN Blogs</a></li>
</ul>
</div>
<div class="section">
<h4>デバイスと画面の向きに関する API</h4>

<ul>
<li><a href="http://msdn.microsoft.com/ja-jp/library/ie/dn433240(v=vs.85).aspx">&#x30C7;&#x30D0;&#x30A4;&#x30B9;&#x306E;&#x5411;&#x304D;&#x306E;&#x30A4;&#x30D9;&#x30F3;&#x30C8; (Windows)</a></li>
<li><a href="http://msdn.microsoft.com/ja-jp/library/ie/dn433241(v=vs.85).aspx">&#x753B;&#x9762;&#x306E;&#x5411;&#x304D;&#x306E; API (Windows)</a></li>
</ul>
</div>
<div class="section">
<h4>高 DPI サポート</h4>
<p><span itemscope itemtype="http://schema.org/Photograph"><img src="20131112071652.png" alt="f:id:daruyanagi:20131112071652p:plain" title="f:id:daruyanagi:20131112071652p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>Windows 8 では高 DPI 環境のサポートが充実しているが、Windows 7 にはこれがない。タブレット使いじゃなくても、Retina ディスプレイなんかを使う人は、Windows 8.1 にしたほうがいいのかもしれない。</p>

<ul>
<li><a href="http://msdn.microsoft.com/ja-jp/library/ie/dn265030(v=vs.85).aspx">&#x9AD8; DPI &#x306E;&#x30B5;&#x30DD;&#x30FC;&#x30C8; (Windows)</a></li>
</ul>
</div>
</div>
<div class="section">
<h3>そのほか</h3>
<p>拡張保護モードはサポートされない。</p>

<ul>
<li><a href="http://msdn.microsoft.com/ja-jp/library/ie/dn265025(v=vs.85).aspx">&#x30C7;&#x30B9;&#x30AF;&#x30C8;&#x30C3;&#x30D7; IE &#x306E;&#x62E1;&#x5F35;&#x4FDD;&#x8B77;&#x30E2;&#x30FC;&#x30C9; (Windows)</a></li>
</ul><p>あと、最新の更新プログラムが適用されていないと、一部の「F12 開発者ツール」がサポートされない。</p>

<ul>
<li><a href="http://msdn.microsoft.com/ja-jp/library/ie/dn255009(v=vs.85).aspx">UI &#x306E;&#x5FDC;&#x7B54;&#x6027;&#x3092;&#x5411;&#x4E0A;&#x3055;&#x305B;&#x308B; (Windows)</a></li>
</ul><p>途中でめんどくさくなったので、単なるリンク集みたいになった。とりあえず、いろいろ違うんだよってことで。</p>

</div>