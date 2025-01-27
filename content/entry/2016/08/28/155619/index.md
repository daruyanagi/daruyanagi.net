---
date: 2016-08-28T15:56:19.0000000
draft: false
title: "艦これのスクリーンショットを撮れるツールを自作した"
tags: ["WPF", "Aoba", "告知"]
eyecatch: 20160828154228.png
---
<p><span itemscope itemtype="http://schema.org/Photograph"><img src="20160828154228.png" alt="f:id:daruyanagi:20160828154228p:plain" title="f:id:daruyanagi:20160828154228p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>お休み中にオンラインストレージの掃除やツールのアップデートをやっていたのだけど、愛用していた艦これのキャプチャーツールが動かなくなったので、WPF で自作した。</p><p><iframe src="//hatenablog-parts.com/embed?url=https%3A%2F%2Fgithub.com%2Fdaruyanagi%2FAoba%2Freleases%2Ftag%2Fv1.0.0" title="daruyanagi/Aoba" class="embed-card embed-webcard" scrolling="no" frameborder="0" style="display: block; width: 100%; height: 155px; max-width: 500px; margin: 10px 0px;"></iframe></p><p>一応自分ところでは動いているのだけど（Windows 10 version 1607＋Visual Studio 2015 Update 3で動作確認）、参照の不足なんかで動かないことがあるかもしれない。</p><p>使い方は</p>

<ul>
<li>一番左の検知ボタンを押してゲーム画面の範囲を検出する</li>
<li>検出に成功すると、キャプチャーボタンが有効化される</li>
<li>キャプチャーボタンを押す</li>
</ul><p>だけ。キャプチャーが成功すると、トーストが出る（なので、Windows 8 以降じゃないと動かないと思う）。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20160828154639.png" alt="f:id:daruyanagi:20160828154639p:plain" title="f:id:daruyanagi:20160828154639p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>トーストをクリックすると、キャプチャーした画像にアクセスできる。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20160828154704.png" alt="f:id:daruyanagi:20160828154704p:plain" title="f:id:daruyanagi:20160828154704p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>一応、頑張った点としては</p>

<ul>
<li>マルチモニター対応（自分が Surface 3 or サブディスプレイで遊んでるので</li>
<li>スケーリングとか拡大表示にも対応してるかも（大きさは決め打ちにしていない
<ul>
<li>ゲーム画面の左上ピクセルかなーって感じのピクセルを探して、そこからある程度デカい矩形を検出</li>
<li>そんな感じで割と適当なのと、ちょっと処理が遅いかなって感じなので、気が向いたら改善するかも</li>
</ul></li>
</ul><p>みたいな感じ。</p><p>簡易なロジック自体は割と簡単にできたけど、UI を整えたりなんだかんだで（WPF でトーストのだしかたわかんねぇ……ぐちゃぐちゃ参照を追加したけど、ここでちょっと間違ってる気がする）、半日ぐらいかかった（<br />
<br />
</p>

<div class="section">
<h4>追伸</h4>
<p>Visual Studio の GitHub 拡張を使ってみたけど、やっぱり自分には GitHub アプリの方が使いやすいかな……。</p><p><iframe src="//hatenablog-parts.com/embed?url=http%3A%2F%2Fforest.watch.impress.co.jp%2Fdocs%2Fnews%2F1015913.html" title="GitHub、「GitHub Extension for Visual Studio 2.0」をリリース" class="embed-card embed-webcard" scrolling="no" frameborder="0" style="display: block; width: 100%; height: 155px; max-width: 500px; margin: 10px 0px;"></iframe><br />
</p>

</div>
<div class="section">
<h4>追記</h4>
<p><iframe src="//hatenablog-parts.com/embed?url=https%3A%2F%2Fgithub.com%2Fdaruyanagi%2FAoba%2Freleases%2Ftag%2Fv1.1.0" title="daruyanagi/Aoba" class="embed-card embed-webcard" scrolling="no" frameborder="0" style="display: block; width: 100%; height: 155px; max-width: 500px; margin: 10px 0px;"></iframe></p><p>タブレットモードでも最前面表示されるように改修。</p>

<ul>
<li>WindowStyle を ToolWindow にする</li>
<li>ShowTaskbar を false にする</li>
</ul><p>でいけるっぽい。</p>

</div>