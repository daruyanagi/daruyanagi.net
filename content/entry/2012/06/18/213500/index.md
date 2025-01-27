---
date: 2012-06-18T21:35:00.0000000
draft: false
title: "8時59分60秒"
tags: ["Windows", "時間"]
eyecatch: 
---
<p><a href="http://www.flickr.com/photos/dominicmeason/4493258276/" title="Astronomical Clock and Death, Prague (With Explanations) by dominicmeason, on Flickr"><img src="http://farm3.staticflickr.com/2720/4493258276_f4ce833a9d.jpg" width="500" height="333" alt="Astronomical Clock and Death, Prague (With Explanations)"></a></p>

<blockquote cite="http://www.soumu.go.jp/menu_news/s-news/01tsushin03_02000031.html">
<p>今年の7月1日は 1秒 長い日となります</p>

<cite><a href="http://www.soumu.go.jp/menu_news/s-news/01tsushin03_02000031.html">&#x7DCF;&#x52D9;&#x7701;&#xFF5C;&#x300C;&#x3046;&#x308B;&#x3046;&#x79D2;&#x300D;&#x633F;&#x5165;&#x306E;&#x304A;&#x77E5;&#x3089;&#x305B;</a></cite>
</blockquote>
<p>今年の7月1日だけ<b>8時59分60秒</b>があるだなんて、ちょっと素敵で不思議。けど、不思議では済まないのが融通の効かない計算機の世界。たったこれだけのことで、計算機の世界はちょっと混乱してしまう。</p>

<blockquote cite="http://support.microsoft.com/kb/2722715/ja">
<p>Windows　<a class="keyword" href="http://d.hatena.ne.jp/keyword/%A5%AA%A5%DA%A5%EC%A1%BC%A5%C6%A5%A3%A5%F3%A5%B0%A5%B7%A5%B9%A5%C6%A5%E0">オペレーティングシステム</a>では、<a class="keyword" href="http://d.hatena.ne.jp/keyword/%A4%A6%A4%EB%A4%A6%C9%C3">うるう秒</a>の処理をおこないません。たとえば、「yyyy/mm/dd 08:59:60」の年月日時刻情報につきましては、Windows OS ではサポートしていません。このため、たとえば「2012/7/1 08:59:60」は「2012/7/1 09:00:00」として処理されます。</p>

<cite><a href="http://support.microsoft.com/kb/2722715/ja">
&#x3046;&#x308B;&#x3046;&#x79D2;&#x306B;&#x95A2;&#x3059;&#x308B;&#x30B5;&#x30DD;&#x30FC;&#x30C8;&#x306B;&#x3064;&#x3044;&#x3066;
</a></cite>
</blockquote>
<p><a href="http://www.infoq.com/jp/news/2012/03/Azure-Blackout-Leap-Year-Bug">InfoQ: Windows Azure &#x304C;&#x3046;&#x308B;&#x3046;&#x5E74;&#x51E6;&#x7406;&#x306E;&#x30D0;&#x30B0;&#x306B;&#x3088;&#x3063;&#x3066;&#x30C0;&#x30A6;&#x30F3;</a> で少し名誉を傷つけられた Microsoft の場合。 </p><p>Windows では、<a class="keyword" href="http://d.hatena.ne.jp/keyword/%A4%A6%A4%EB%A4%A6%C9%C3">うるう秒</a>については基本的に対応せず、2012/7/1 08:59:60 は存在しないものとして扱われる。必然的に1秒のズレが生じるが、一般的な用途ではあまり問題がない。1秒のズレは、いずれかのタイミングで“time.windows.com”<a href="#f1" name="fn1" title="ほかのNTPサーバーへカスタマイズすることも可能">*1</a>と同期され、ユーザーが気づかないうちにこっそり自動補正される。</p><p>けれど、まったく問題がないわけではない。「2012/7/1 08:59:60」を扱うシステムが Windows と連携する場合は、なにか起こるかもしれない。</p><p>たとえば、Microsoft <a class="keyword" href="http://d.hatena.ne.jp/keyword/SQL%20Server">SQL Server</a> は「2012/7/1 08:59:60」というデータの入力を受け付けないけれど、それを行おうとしてハングアップしてしまうアプリケーションがないとはいえない。</p>

<blockquote>
<p>内部動作とは別に、外部から<a class="keyword" href="http://d.hatena.ne.jp/keyword/%A4%A6%A4%EB%A4%A6%C9%C3">うるう秒</a>を加味した時刻を受け取る可能性がある例として iCalendar 形式の予定がありますが、<a class="keyword" href="http://d.hatena.ne.jp/keyword/Exchange%20Server">Exchange Server</a> が iCalendar 形式の予定を受信する際、時刻の表記は RFC5545 に定義されている形式のみをサポートします。<a class="keyword" href="http://d.hatena.ne.jp/keyword/%A4%A6%A4%EB%A4%A6%C9%C3">うるう秒</a>を考慮した秒の表記は 0 から 60 までがサポートされ、それ以上の秒数が記述されている場合は不正な形式として処理され、正しい iCalendar 形式とは見なされません。</p><p>Outlook につきましては、60 秒の場合は 0 とみなしますので、2012/07/01 08:59:60 は、2012/07/01 08:59:00 となり、最大で 1 分のずれが生じる可能性がございます。<br />
メールの受信の順番がずれて見える可能性がございますが、動作に影響はありません。</p>

</blockquote>
<p>この程度のエラーならかわいいものだけど。</p><p>また、NTP サーバーと同期を行う一部の <a class="keyword" href="http://d.hatena.ne.jp/keyword/UNIX">UNIX</a>系のOSでは部影響があるようだ。</p>

<blockquote cite="http://jp.fujitsu.com/platform/server/unix/soft/time2009-solaris-server.pdf">
<p>時刻差を強制的に同期させるモード（STEPモード）では、<a class="keyword" href="http://d.hatena.ne.jp/keyword/%A4%A6%A4%EB%A4%A6%C9%C3">うるう秒</a>挿入のタイミングでミリ秒単位の時刻の逆進が発生しますので、ミリ秒単位で時刻を扱っているミドルウェアやアプリケーションへ影響が生じる可能性があります。</p><p><small>2009年1月1日の「<a class="keyword" href="http://d.hatena.ne.jp/keyword/%A4%A6%A4%EB%A4%A6%C9%C3">うるう秒</a>」挿入に伴う<a class="keyword" href="http://d.hatena.ne.jp/keyword/%C9%D9%BB%CE%C4%CC">富士通</a><a class="keyword" href="http://d.hatena.ne.jp/keyword/Solaris">Solaris</a>サーバへの影響について</small></p>

<cite><a href="http://jp.fujitsu.com/platform/server/unix/soft/time2009-solaris-server.pdf">http://jp.fujitsu.com/platform/server/unix/soft/time2009-solaris-server.pdf</a></cite>
</blockquote>

<ul>
<li>STEPモード：<a class="keyword" href="http://d.hatena.ne.jp/keyword/%A4%A6%A4%EB%A4%A6%C9%C3">うるう秒</a>挿入のタイミングでミリ秒単位の時刻の逆進が発生</li>
<li>SLEWモード：<a class="keyword" href="http://d.hatena.ne.jp/keyword/%A4%A6%A4%EB%A4%A6%C9%C3">うるう秒</a>挿入のタイミングで逆進が発生しないように時刻差をゆっくり合わせる</li>
</ul><p>本来、時間というものは順番に来るもので、当然、アプリケーションは暗黙にそれを前提としている。なので、たとえミリ秒単位であったとしても、逆進が起こるのはあまり望ましくない。そんなわけで、なかにはちまちま<a class="keyword" href="http://d.hatena.ne.jp/keyword/%A4%A6%A4%EB%A4%A6%C9%C3">うるう秒</a>を挿入しないで、あとでまとめてドバっと調整してしまおうぜ、という意見もあるらしい（<a href="http://science.slashdot.jp/story/10/08/26/0424227/%E3%80%8C%E3%81%86%E3%82%8B%E3%81%86%E7%A7%92%E3%80%8D%E5%BB%83%E6%AD%A2%E3%81%B8--ITU-%E3%81%8C%E6%96%B0%E6%96%B9%E5%BC%8F%E3%82%92%E6%A4%9C%E8%A8%8E%E4%B8%AD">&#x300C;&#x3046;&#x308B;&#x3046;&#x79D2;&#x300D;&#x5EC3;&#x6B62;&#x3078; ? ITU &#x304C;&#x65B0;&#x65B9;&#x5F0F;&#x3092;&#x691C;&#x8A0E;&#x4E2D; | &#x30B9;&#x30E9;&#x30C3;&#x30B7;&#x30E5;&#x30C9;&#x30C3;&#x30C8;&#x30FB;&#x30B8;&#x30E3;&#x30D1;&#x30F3; &#x30B5;&#x30A4;&#x30A8;&#x30F3;&#x30B9;</a>）。</p><p>たった一秒でも、いろんな議論があるもんだ。たった一秒の Leapなど、ほとんどの人は意識しなければ気づかないだろうのに。 </p>
<div class="footnote">
<p class="footnote"><a href="#fn1" name="f1" class="footnote-number">*1</a><span class="footnote-delimiter">:</span><span class="footnote-text">ほかのNTPサーバーへカスタマイズすることも可能</span></p>
</div>