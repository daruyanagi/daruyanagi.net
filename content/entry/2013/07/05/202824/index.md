---
date: 2013-07-05T20:28:24.0000000
draft: false
title: "Windows 8.1 RT: 新しい SkyDrive は新しかった"
tags: ["Windows 8.1", "SkyDrive"]
eyecatch: 20130705174449.png
---
<p><span itemscope itemtype="http://schema.org/Photograph"><img src="20130705174449.png" alt="f:id:daruyanagi:20130705174449p:plain" title="f:id:daruyanagi:20130705174449p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>Windows 8.1<a href="#f1" name="fn1" title="筆者は Surface RT でプレビュー版を試用しているので、厳密には Windows 8.1 RT である">*1</a> では SkyDrive がシステムに組み込まれ、PC（ローカルストレージ）と並ぶ“第一級ストレージ”になっている。あくまでも“追加ストレージ”だった Windows 8.0 以前とは、仕組みも機能も重要性もまったく異なる。</p>


<div class="section">
<h3>Windows 8.1 の SkyDrive を構成するモノ</h3>
<p>とりあえず、今回登場するプレイヤーを紹介しておこう。</p>

<div class="section">
<h4>SkyDrive.exe</h4>
<p><span itemscope itemtype="http://schema.org/Photograph"><img src="20130705191534.png" alt="f:id:daruyanagi:20130705191534p:plain" title="f:id:daruyanagi:20130705191534p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>これまで AppData でほかの一般社員と机を並べて働いていたが、 今回の組織改編では Windows 直属の System32 という社内の最重要部署にデスクを与えられた。やる気満々の若手ホープ。</p>

</div>
<div class="section">
<h4>FileManager.exe</h4>
<p><span itemscope itemtype="http://schema.org/Photograph"><img src="20130705191553.png" alt="f:id:daruyanagi:20130705191553p:plain" title="f:id:daruyanagi:20130705191553p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>今年採用された新入社員<a href="#f2" name="fn2" title="たぶん。Windows 8.0 Pro 環境では見つからなかった">*2</a>。なんと Windows フォルダ在住で、自分だけのフォルダまでもっている。今のところその任務は明らかではないが<a href="#f3" name="fn3" title="いやぁ、ARM では分析するにもアプリがなくってさ！">*3</a>、なにか極秘の命令を受けて独自に行動しているのは確かだ。</p><p>（もしかしたら、これってストア アプリ「SkyDrive」の実体なのかなぁ。そういえば、「SkyDrive」ってなぜか「タスク マネージャー」の［アプリの履歴］タブに出てこない。そういう意味でも、ちょっと特殊な作りなんだな）</p>

</div>
<div class="section">
<h4>［PC の設定］－［SkyDrive］</h4>
<p><span itemscope itemtype="http://schema.org/Photograph"><img src="20130705191615.png" alt="f:id:daruyanagi:20130705191615p:plain" title="f:id:daruyanagi:20130705191615p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>裏でコソコソ働くのを好む根暗な SkyDrive.exe と FileManager.exe の世話をみる母親的存在。やさしくタッチしてあげると、彼らに言伝てしてくれる。</p>

</div>
<div class="section">
<h4>Windows ストア アプリ「SkyDrive」</h4>
<p><span itemscope itemtype="http://schema.org/Photograph"><img src="20130705194942.png" alt="f:id:daruyanagi:20130705194942p:plain" title="f:id:daruyanagi:20130705194942p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>忘れてはいけないのは、Windows ストア アプリの「SkyDrive」さん。イマーシブアプリからのアクセス要求をすべてサバく、メガネっ娘のかわいらしい事務職。今回のシステムアップデートではローカルドライブとの同期にも関わることになったので、かなり忙しくなりそう。</p>

</div>
</div>
<div class="section">
<h3>まったく新しくなった同期の仕組み</h3>
<p>Windows 8.0 の SkyDrive では、以下の二つの機能が利用できた。</p>

<ul>
<li>すべてを同期</li>
<li>フォルダを選択して同期（<a href="http://www.forest.impress.co.jp/docs/news/20121116_573501.html">&#x7A93;&#x306E;&#x675C; - &#x3010;NEWS&#x3011;&#x30C7;&#x30B9;&#x30AF;&#x30C8;&#x30C3;&#x30D7;&#x5411;&#x3051;&#x300C;SkyDrive&#x300D;&#x304C;&#x30A2;&#x30C3;&#x30D7;&#x30C7;&#x30FC;&#x30C8;&#x3001;&#x540C;&#x671F;&#x3059;&#x308B;&#x30D5;&#x30A9;&#x30EB;&#x30C0;&#x3092;&#x9078;&#x629E;&#x53EF;&#x80FD;&#x306B;</a>）</li>
</ul><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20130705192549.png" alt="f:id:daruyanagi:20130705192549p:plain:w540" title="f:id:daruyanagi:20130705192549p:plain:w540" class="hatena-fotolife" style="width:540px" itemprop="image"></span></p><p>どちらを利用するかはセットアップ時に選択できるし、あとから変更することもできる。</p><p>一方、Windows 8.1 の SkyDrive では以下の二つが利用できる。</p>

<ul>
<li>オンラインで利用する（初期設定）</li>
<li>常にオフラインで利用する</li>
</ul><p>オンラインで利用する場合、ファイルはオンデマンドでダウンロードされるため、ネットワークにつながっていないと利用できない。「エクスプローラー」ではあたかも C:\Users\***\SkyDrive にファイルが存在するようにみえるが、実際はファイルエントリを示しているだけのようだ。</p><p>要するにリアルなファイルシステムではなく、バーチャルなファイルシステムになっている。</p><p>（正確にいうと、リパースポイントと呼ばれる機能が利用されている。この機能は Windows 2000 出はじめて搭載された）</p><p>実際のファイルを同期（<b>直接同期</b>）するオンラインストレージとしては、以前の SkyDrive や Dropbox が挙げられる。仕組みは比較的シンプルだが、ファイルそのものをストレージに保存するため、そのファイル分だけローカルストレージを消費してしまう。フォルダ単位の選択同期はそれを解決する一つの手段だが、それでもユーザー側で同期するフォルダと同期しないフォルダを管理しなければならない。</p><p>仮想ファイルシステムの仕組み（<b>間接同期</b>）は、今は亡き「ZumoDrive」（<a href="http://www.forest.impress.co.jp/article/2009/03/05/zumodrive.html">&#x7A93;&#x306E;&#x675C; - &#x3010;REVIEW&#x3011;&#x8907;&#x6570;PC&#x3067;&#x30D5;&#x30A1;&#x30A4;&#x30EB;&#x3092;&#x81EA;&#x52D5;&#x540C;&#x671F;&#x30FB;&#x5171;&#x6709;&#x3067;&#x304D;&#x308B;&#x30B9;&#x30C8;&#x30EC;&#x30FC;&#x30B8;&#x30B5;&#x30FC;&#x30D3;&#x30B9;&ldquo;ZumoDrive&rdquo;</a>）などで採用されていた。ファイルを置いておく必要がなく、ローカルストレージを無駄に消耗しないのがメリットだが、逆に言えばファイルをロードするたびにネットワークアクセスが発生するのがデメリット。オフラインだと利用できないし、ファイルのロードが遅い。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20130705195010.png" alt="f:id:daruyanagi:20130705195010p:plain" title="f:id:daruyanagi:20130705195010p:plain" class="hatena-fotolife" itemprop="image"></span></p>

<ul>
<li><a href="http://answers.microsoft.com/ja-jp/windows/forum/windows8_1_pr-files/%E4%B8%80%E9%83%A8%E3%81%AE-skydrive/2efa3293-71a7-44d2-bc89-1b9588df9b7c">&#x4E00;&#x90E8;&#x306E; SkyDrive &#x30D5;&#x30A1;&#x30A4;&#x30EB;&#x304C;&#x6DE1;&#x8272;&#x8868;&#x793A;&#x3055;&#x308C;&#x3001;&#x4F7F;&#x7528;&#x3067;&#x304D;&#x306A;&#x3044;&#x306E;&#x306F;&#x306A;&#x305C;&#x3067;&#x3059;&#x304B;&#xFF1F; - &#x30DE;&#x30A4;&#x30AF;&#x30ED;&#x30BD;&#x30D5;&#x30C8; &#x30B3;&#x30DF;&#x30E5;&#x30CB;&#x30C6;&#x30A3;</a></li>
</ul><p>ただし、ある程度のバッファーを用意しておき、よく利用するファイルだけをキャッシュしておけば、そのデメリットは軽減できる（<b>キャッシュありの間接同期</b>）。これは所謂“80対20の法則”（全体の 20 ％ が利用頻度の 80 ％を占める）を利用した賢いやり方だが、メカニズムはキャッシュ管理の分だけ複雑になり、クライアントが不安定になる恐れがある。</p><p>新しい SkyDrive では、<b>キャッシュあり（？）の間接同期（オンライン利用）</b>（初期設定、詳細なオプションはなし）とファイル・フォルダごとの<b>直接同期（オフライン利用）</b>をユーザー側で切り替えられる。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20130705194157.png" alt="f:id:daruyanagi:20130705194157p:plain:w540" title="f:id:daruyanagi:20130705194157p:plain:w540" class="hatena-fotolife" style="width:540px" itemprop="image"></span></p><p>「エクスプローラー」の場合はコンテキストメニューから。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20130705200227.png" alt="f:id:daruyanagi:20130705200227p:plain:w540" title="f:id:daruyanagi:20130705200227p:plain:w540" class="hatena-fotolife" style="width:540px" itemprop="image"></span></p><p>ストア アプリの場合はアプリバーから。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20130705201355.png" alt="f:id:daruyanagi:20130705201355p:plain:w540" title="f:id:daruyanagi:20130705201355p:plain:w540" class="hatena-fotolife" style="width:540px" itemprop="image"></span></p><p>ストア アプリの［設定］チャームから、すべてのファイルをオフライン化することも可能。</p><p>32GB モデルの Surface RT など、ローカルストレージの空き容量に不安がある場合はオンライン利用が有効。ただし、ネットワークが必須なので、頻繁に利用するフォルダやファイルはあらかじめ手動でオフライン利用を有効にしておく必要がある。一方、大容量 HDD を搭載した比較的ストレージに余裕のある大型ノート PC やデスクトップ PC では、すべてのオフライン利用が有効だろう。</p><p>あと、注意というほどでもないのだが、オフライン利用とオンライン利用の切り替えはそれほど気楽に行えるものではない。とくにファイルの多いフォルダを切り替えると、アップロードやダウンロードに時間がかかり、その間（<b>保留状態</b>）は再度元に戻すことができない。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20130705195023.png" alt="f:id:daruyanagi:20130705195023p:plain" title="f:id:daruyanagi:20130705195023p:plain" class="hatena-fotolife" itemprop="image"></span></p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20130705193238.png" alt="f:id:daruyanagi:20130705193238p:plain" title="f:id:daruyanagi:20130705193238p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>また、以上の記述は Windows 8.1 RT を元にしており、Windows 8.0 からアップデートした場合どうなるかは正確には把握していない。デスクトップ版「SkyDrive」がすでにインストールされている環境だとややこしそうだ。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20130705201858.png" alt="f:id:daruyanagi:20130705201858p:plain" title="f:id:daruyanagi:20130705201858p:plain" class="hatena-fotolife" itemprop="image"></span></p>

<ul>
<li><a href="http://answers.microsoft.com/ja-jp/windows/forum/windows8_1_pr-files/windows-81-preview-%E3%81%A7-skydrive/631f2467-536c-4156-ae93-2a4ff83e38a7">Windows 8.1 Preview &#x3067; SkyDrive &#x30D5;&#x30A1;&#x30A4;&#x30EB;&#x304C;&#x4F7F;&#x7528;&#x3067;&#x304D;&#x308B;&#x304B;&#x3069;&#x3046;&#x304B;&#x3092;&#x6C7A;&#x3081;&#x308B;&#x8981;&#x56E0;&#x306F;&#x4F55;&#x3067;&#x3059;&#x304B;&#x3002; - &#x30DE;&#x30A4;&#x30AF;&#x30ED;&#x30BD;&#x30D5;&#x30C8; &#x30B3;&#x30DF;&#x30E5;&#x30CB;&#x30C6;&#x30A3;</a></li>
</ul><p>ちなみに SkyDrive には細かい制限事項（ファイル数や単体ファイルのサイズ、ファイルの名前などなど）があるのだけど、これについてはまだ検証できていないので、また機会を改めて。</p>

</div>
<div class="section">
<h3>同期プロセスはストア アプリで</h3>
<p><span itemscope itemtype="http://schema.org/Photograph"><img src="20130705192253.png" alt="f:id:daruyanagi:20130705192253p:plain:w540" title="f:id:daruyanagi:20130705192253p:plain:w540" class="hatena-fotolife" style="width:540px" itemprop="image"></span></p><p>Windows 8.0 の SkyDrive では、タスクトレイアイコンから同期プロセスの進捗状況が確認できた。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20130705192726.png" alt="f:id:daruyanagi:20130705192726p:plain:w540" title="f:id:daruyanagi:20130705192726p:plain:w540" class="hatena-fotolife" style="width:540px" itemprop="image"></span></p><p>一方、Windows 8.1 の SkyDrive にはタスクトレイのユーザーインターフェイスがなく、Windows ストア アプリ「SkyDrive」がその役割を担う。これは評価が二分するだろう。ストア アプリは気軽ではないし、進捗状況の確認向けのインターフェイスではない。しかし、ダウンロード中のファイルやアップロード中のファイルがタイルで一覧できるのは評価できるかもしれない。タスクトレイのポップアップウィンドウよりは情報量が多い。</p>

</div>
<div class="section">
<h3>特権的な地位への懸念</h3>
<p>このように、バックエンドであれ、設定画面であれ、ストア アプリであれ、Windows 8.1 の SkyDrive には一般のアプリよりも一つ抜きんでた特権的な地位が与えられているのがわかる。確かに、これのおかげで――とくに Windows RT は――便利になった。</p><p>しかし気になるのが、ほかのアプリケーションとの兼ね合いだ。</p><p>オンラインストレージサービスは腐るほどあり、互いに切磋琢磨してる。そのなかで SkyDrive だけが特権的な地位を占めている。これはほかのサービスにとって愉快なことではないだろう。下手すれば、往年のように独占禁止法違反で訴えられるかもしれない。</p><p>また SkyDrive よりも Dropbox などのほかのサービスを好むユーザーにとっても、あまり納得できる解決ではない。個人的には SkyDrive で満足しているが、機能面ではまだまだ Dropbox のほうが上だと感じるユーザーは多い。Microsoft 以外のプラットフォームではなおさらだ。</p><p>個人的には、デスクトップアプリやバックグラウンドアプリに対しても、なんらかの認定基準を設けてストアで公開できるようになればいいと思うが、なかなか難しいのだろうか。</p>

</div>
<div class="section">
<h3>次回予告</h3>
<p>実は Widnows 8.1 の SkyDrive のルートフォルダは C:\Users\***\SkyDrive 固定で、変更できない。次回はこれを SD カードに移動させてみようかなと思う。あわせて、Windows 8.1 と SD カードドライブについても少し書きたい。</p>

</div><div class="footnote">
<p class="footnote"><a href="#fn1" name="f1" class="footnote-number">*1</a><span class="footnote-delimiter">:</span><span class="footnote-text">筆者は Surface RT でプレビュー版を試用しているので、厳密には Windows 8.1 RT である</span></p>
<p class="footnote"><a href="#fn2" name="f2" class="footnote-number">*2</a><span class="footnote-delimiter">:</span><span class="footnote-text">たぶん。Windows 8.0 Pro 環境では見つからなかった</span></p>
<p class="footnote"><a href="#fn3" name="f3" class="footnote-number">*3</a><span class="footnote-delimiter">:</span><span class="footnote-text">いやぁ、ARM では分析するにもアプリがなくってさ！</span></p>
</div>