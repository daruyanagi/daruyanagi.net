---
date: 2014-06-16T16:32:54.0000000
draft: false
title: "プログラミング生放送勉強会 第29回＠サイボウズ株式会社 松山オフィス #pronama 無事終了……！"
tags: ["勉強会"]
eyecatch: 
---
<p><span itemscope itemtype="http://schema.org/Photograph"><img src="20140614095716.jpg" alt="f:id:daruyanagi:20140614095716j:plain" title="f:id:daruyanagi:20140614095716j:plain" class="hatena-fotolife" itemprop="image"></span></p><p>まぁ、本当に「無事」かどうかはわかりませんが（段取りよくなくて迷惑かけたところも少なからずあり）、とりあえず終わりました。この街に移るにあたって、プロ生を成功させることは自分に課して、またみんなの前でもやると表明した一つの公約でもあったので、ちょっと肩の荷が下りた感じ。</p><p>でも、どうだったかな？　人数を集めるという点では成功した（東京換算<a href="#f-c6bf52f9" name="fn-c6bf52f9" title="@jz5 によって定式化された公式による">*1</a>で300人ぐらい集まりました）と思うけれど、みんなに楽しんでもらえたかどうか。別に人数を集めるのが目的じゃないし、デカいのを一つデキればいいというわけじゃないわけで。みんなのモチベーションを作っていける継続的な場になって初めて、成功と言えるような気もしてきました。</p><p>これは @nakaji とも少し話したのだけど、これからも小規模な勉強会（という名の飲み会）を継続してやって、その中から参加者や登壇者が出るような流れも作れたらいいなぁ。今回 LT をやってもらった <a href="https://twitter.com/yurufuwarb">&#x3086;&#x308B;&#x3075;&#x308F;.rb (@yurufuwarb) | Twitter</a> さんにお邪魔してみるのもアリなのかな（Ruby は素人レベルだけど）。酒を飲みながら、ほかの会場のプロ生へオンラインで突っ込みを入れるサテライト勉強会構想や、なにかテーマを決めてまったりお勉強する構想なんかも考えていますが……実現するかな？ｗ</p><p>それはまぁ、ともかく。</p>

<div class="section">
<h3>サイボウズ株式会社 松山オフィス</h3>
<p><a href="http://pronama.azurewebsites.net/2014/03/29/pronama-29-at-matsuyama/">6/14 &#x30D7;&#x30ED;&#x30B0;&#x30E9;&#x30DF;&#x30F3;&#x30B0;&#x751F;&#x653E;&#x9001;&#x52C9;&#x5F37;&#x4F1A; &#x7B2C;29&#x56DE;&#xFF20;&#x30B5;&#x30A4;&#x30DC;&#x30A6;&#x30BA;&#x682A;&#x5F0F;&#x4F1A;&#x793E; &#x677E;&#x5C71;&#x30AA;&#x30D5;&#x30A3;&#x30B9; &#x958B;&#x50AC;&#xFF01; #pronama &ndash; &#x30D7;&#x30ED;&#x30B0;&#x30E9;&#x30DF;&#x30F3;&#x30B0;&#x751F;&#x653E;&#x9001;</a></p><p>今回はサイボウズ株式会社 松山オフィスを貸していただきました。ありがとうございます。場所は、大街道の松山中央郵便局の近く。“五志喜”の向かい側と言えば、わかる人はわかるかも。</p><p>今まで知らなかったんですけど、サイボウズって松山が創業の地なんですね。なんで東京・大阪と並んで松山オフィスがあるのか、割と謎に思ってました（</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20140614100619.jpg" alt="f:id:daruyanagi:20140614100619j:plain" title="f:id:daruyanagi:20140614100619j:plain" class="hatena-fotolife" itemprop="image"></span></p><p>会場設営の様子。めっちゃおしゃれな部屋だったのですけれど、50人入るには少し手狭だったので、机を搬出しりたりしました。机が当たらなかった人には申し訳ない感じ。</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20140614100510.jpg" alt="f:id:daruyanagi:20140614100510j:plain" title="f:id:daruyanagi:20140614100510j:plain" class="hatena-fotolife" itemprop="image"></span></p><p>あと、なかじがつくった ASP.NET MVC 製のチェックインシステムが大活躍。割りと受付が楽になった。ネットワークなしで動作＋チェックインしたら一覧から削除が実現したら、本格的に全国の勉強会でも使えそう。</p><p><a href="http://nakaji.hatenablog.com/entry/2014/06/12/072000">&#x53D7;&#x4ED8;&#x30A2;&#x30D7;&#x30EA;&#x306E;&#x53C2;&#x52A0;&#x8005;&#x767B;&#x9332;&#x304C;&#x624B;&#x5165;&#x529B;&#x4E0D;&#x8981;&#x306B;&#x306A;&#x308A;&#x307E;&#x3057;&#x305F; - &#x306A;&#x304B;&#x65E5;&#x8A18;</a><br />
</p>

</div>
<div class="section">
<h3>セッション</h3>
<p>注：以下はセッションの解説ではありません。もしかしたら感想ですらありません。セッションを聞いて、自分が何となく思いついたこと・連想したことなどデス。</p>

<div class="section">
<h4>一日に100回デプロイできる開発環境の作り方</h4>
<p><iframe src="https://www.slideshare.net/slideshow/embed_code/key/KbazJu3y4A4CQQ" width="427" height="356" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC; border-width:1px; margin-bottom:5px; max-width: 100%;" allowfullscreen> </iframe> <div style="margin-bottom:5px"> <strong> <a href="https://www.slideshare.net/tomohn/1100-pronama" title="【プロ生松山】1日に100回デプロイできる開発環境の作り方 #pronama " target="_blank">【プロ生松山】1日に100回デプロイできる開発環境の作り方 #pronama </a> </strong> from <strong><a href="https://www.slideshare.net/tomohn" target="_blank">智治 長沢</a></strong> </div></p><p>アトラシアンのエヴァンジェリスト @tomohn さんのセッション。タイトルは“羊頭”（釣りともいうｗ）でしたが、中身は“狗肉”にあらず。聴衆を巻き込んでいくスタイルは見事だなぁ、と思いました。</p><p>実は @tomohn さんのセッション、個人的に聞きたかったので、僕が参加を予定していた仙台か松山のプロ生にはきていただこうと思って、だいぶ前から手を回していました。</p><p>というのも、“継続的に価値を作り出す”とか“ソフトウェアの産地直送”みたいな開発の在り方がこれから主流になるだろうというのは理解しているつもりなのですが、どんなツールがどんなふうに使われているのかというのは、実務には関係のない僕にはこういう機会じゃないと触れられないので。耳学問がしたかったんですよね。</p><p>集団的な開発手法が洗練されていくことっていうのは、個人にだって大いに関係があります。実際に“ラピッドリリース”という形で恩恵を受けていたりするし、開発環境や周辺ツールが高機能化したり、無償で開放されたりする。自分はそういう製品の記事も書かなきゃいけなかったりするのだけど、そういうとき、ただ便利だ！　無料だ！　ヒャッハーー！ってだけじゃなくて、その製品が大きなトレンドの中でどういう位置を占めているのかなのかもちゃんと把握できなきゃいけない（仮に記事に直接書かなくてもな）。そういうことを怠ると、すぐに頓珍漢なことを書いて Twitter や はてブ で晒しあげられたりするハメになるしねｗ </p><p>あと、ソフトウェア開発の世界にはバックグラウンドに経営学があり、その裏にはまたミクロ経済学や“組織の経済”なんかの知識が控えている。大学時代にそういう世界へ興味を持っていたものとして、それがどんな感じに実際の社会に表出しているのかということにはとても興味があるのです。よい成果を持続的に生み出せるようにチーム（共同体）を設計・運用したいというのは、なにもソフトウェア開発の世界だけじゃないですよね？　</p><p><a href="http://re-workstyle.com/articles/pronama-matsuyama-614/">6.14 &#x30D7;&#x30ED;&#x30B0;&#x30E9;&#x30DF;&#x30F3;&#x30B0;&#x751F;&#x653E;&#x9001;&#x52C9;&#x5F37;&#x4F1A;&#xFF20;&#x677E;&#x5C71;&#x3067;&#x8B1B;&#x6F14;&#x3057;&#x307E;&#x3059;</a><br />
</p>

</div>
<div class="section">
<h4>お昼ご飯</h4>
<p><span itemscope itemtype="http://schema.org/Photograph"><img src="20140614121819.jpg" alt="f:id:daruyanagi:20140614121819j:plain" title="f:id:daruyanagi:20140614121819j:plain" class="hatena-fotolife" itemprop="image"></span></p><p>“五志喜”で宇和島鯛めし！</p><p><span itemscope itemtype="http://schema.org/Photograph"><img src="20140614121948.jpg" alt="f:id:daruyanagi:20140614121948j:plain" title="f:id:daruyanagi:20140614121948j:plain" class="hatena-fotolife" itemprop="image"></span></p><p><a href="https://blog.daruyanagi.jp/entry/2014/05/13/001326">GW: &#x5929;&#x8D66;&#x5712;&#x3067;&#x3054;&#x308D;&#x3054;&#x308D;&#x3057;&#x3066;&#x3001;&#x5B87;&#x548C;&#x5CF6;&#x306E;&#x9BDB;&#x3081;&#x3057;&#x98DF;&#x3063;&#x305F;&#x3063;&#x305F;&#x3002; - &#x3060;&#x308B;&#x308D;&#x3050;</a> 以来、宇和島の鯛めしのファンになってしまっている。</p>

</div>
<div class="section">
<h4>いろいろな Windows Runtime API</h4>
<p><iframe src="https://www.slideshare.net/slideshow/embed_code/key/2Ia9KWlgONHve" width="427" height="356" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC; border-width:1px; margin-bottom:5px; max-width: 100%;" allowfullscreen> </iframe> <div style="margin-bottom:5px"> <strong> <a href="https://www.slideshare.net/garicchi/windows-runtimeapi" title="いろいろなWindows runtimeapi" target="_blank">いろいろなWindows runtimeapi</a> </strong> from <strong><a href="https://www.slideshare.net/garicchi" target="_blank">Ryota Togai</a></strong> </div></p><p>まさか地を這ってくるとは思わなんだ。遠いところ申し訳ない。</p><p><a href="http://garicchi.hatenablog.jp/entry/2014/06/15/212502">&#x7B2C;29&#x56DE;&#x30D7;&#x30ED;&#x30B0;&#x30E9;&#x30DF;&#x30F3;&#x30B0;&#x751F;&#x653E;&#x9001;@&#x677E;&#x5C71;&#x3067;&#x767B;&#x58C7;&#x3057;&#x3066;&#x304D;&#x307E;&#x3057;&#x305F; - &#x304C;&#x308A;&#x3089;&#x307C;</a></p><p><blockquote class="twitter-tweet" lang="ja"><p>あ ヘルスビル行くの忘れてた</p>&mdash; がりっち (@garicchi) <a href="https://twitter.com/garicchi/statuses/478078684046172160">2014, 6月 15</a></blockquote><script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script></p><p>関係ないけど @garicchi に早く彼女ができますように。</p>

</div>
<div class="section">
<h4>メンテナブルな JS ってなんだろう</h4>
<p>サイボウズの @datomotu さんのセッション。いかに自分が恨まれないようにしながら、チーム内で共通のルール（コーディングスタイルとか）を確立するして押し付けるかという生々しいお話は、大変参考になった（違</p><p><blockquote class="twitter-tweet" lang="ja"><p>初めから参加してる場合はいいけど、あとからチームに参加する人をみんなのレベルへ引き上げるにはどうすればいいんだろう</p>&mdash; ご注文はだるやなぎですか？ (@daruyanagi) <a href="https://twitter.com/daruyanagi/statuses/477686206746988546">2014, 6月 14</a></blockquote><script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script></p><p>けれど、本筋とは関係ないのだけど、途中から参加するメンバーがいたり、メンバーの出入りが激しい場合はどうすればよいのだろう。</p><p>同じ構成員でスタートできる場合、ルールをみんなで決めることはメンバーの参加者意識を高めるうえで有用だし、輪講などを開催してメンバーのコーディングレベルを高めるのも有効だ。けれど、あとから参加するとそういうことは難しい。自分が参画したわけでもないルールの従うのは苦痛だし、レベルが低い人一人を引き上げるために全員が貢献するのも、最初はともかく継続が難しい。</p><p>懇親会のときに少し聞いてみたけれど、まだそういうケースは体験してないそうで、これからの課題になりそう。</p>

</div>
<div class="section">
<h4>無償版 Visual Studio でいろいろ Web 開発</h4>
<p><a href="http://www.slideshare.net/kiyokura/visual-studioweb-35861495">&#x7121;&#x511F;&#x7248;Visual Studio&#x3067;&#x3044;&#x308D;&#x3044;&#x308D;Web&#x958B;&#x767A;</a></p><p>@kiyokura さん。「Visual Studio 2013 Express for Web Update 2」＋「Web Essentials 2013」拡張機能の組み合わせが、無償でできる Web 開発において最強ということが証明されました。</p><p><blockquote class="twitter-tweet" lang="ja"><p>Visual Studio 便利じゃねーか。WebMatrix 使ってる場合じゃねえ <a href="https://twitter.com/search?q=%23pronama&amp;src=hash">#pronama</a></p>&mdash; ご注文はだるやなぎですか？ (@daruyanagi) <a href="https://twitter.com/daruyanagi/statuses/477691531378184192">2014, 6月 14</a></blockquote><script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script></p><p>「Web Essentials」が無償版でも使えることは知ってたのだけど、JavaScript をここまで変態的（褒め言葉）にコード保管してくれるとは。そろそろ本格的に WebMatrix は要らなくなりそう。［このフォルダを Web サイトとして開く］ツールだけ作って Visual Studio に乗り換えようかなぁ。</p><p><a href="http://kiyokura.hateblo.jp/entry/2014/06/03/222122">Web Essentials 2013 &#x304C;VS2013 Express for Web&#x3067;&#x3082;&#x4F7F;&#x3048;&#x308B;&#x3088;&#x3046;&#x306B;&#x306A;&#x3063;&#x3066;&#x3044;&#x305F;&#x4EF6; - &#x304D;&#x3088;&#x304F;&#x3089;&#x306E;&#x5099;&#x5FD8;&#x9332;</a><br />
</p>

</div>
<div class="section">
<h4>Build より TechEd のが面白かった件</h4>
<p><a href="http://www.slideshare.net/shibayan/build-teched">http://www.slideshare.net/shibayan/build-teched</a></p><p>松山までわざわざ俺を社会的に殺害しにきた件。</p><p><blockquote class="twitter-tweet" lang="ja"><p>プライバシー <a href="https://twitter.com/search?q=%23%E3%81%A8%E3%81%AF&amp;src=hash">#とは</a> <a href="https://twitter.com/search?q=%23pronama&amp;src=hash">#pronama</a></p>&mdash; ご注文はだるやなぎですか？ (@daruyanagi) <a href="https://twitter.com/daruyanagi/statuses/477717533722566658">2014, 6月 14</a></blockquote><script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script></p><p><a href="http://shiba-yan.hatenablog.jp/entry/20140616/1402887936">&#x30D7;&#x30ED;&#x751F;&#x677E;&#x5C71;&#x3067; ASP.NET vNext &#x306B;&#x3064;&#x3044;&#x3066;&#x8A71;&#x3057;&#x3066;&#x304D;&#x307E;&#x3057;&#x305F; - &#x3057;&#x3070;&#x3084;&#x3093;&#x96D1;&#x8A18;</a><br />
</p>

</div>
</div>
<div class="section">
<h3>ライトニングトーク</h3>
<p>あー、もう書くの疲れた！（また今度時間があれば書くかも）　あとは、</p>

<ul>
<li><a href="http://nakaji.hatenablog.com/entry/2014/06/16/021141">&#x30D7;&#x30ED;&#x30B0;&#x30E9;&#x30DF;&#x30F3;&#x30B0;&#x751F;&#x653E;&#x9001;&#x52C9;&#x5F37;&#x4F1A; &#x7B2C;29&#x56DE;&#xFF20;&#x30B5;&#x30A4;&#x30DC;&#x30A6;&#x30BA;&#x682A;&#x5F0F;&#x4F1A;&#x793E; &#x677E;&#x5C71;&#x30AA;&#x30D5;&#x30A3;&#x30B9; &#x3092;&#x958B;&#x50AC; #pronama - &#x306A;&#x304B;&#x65E5;&#x8A18;</a></li>
</ul><p>にお任せしちゃおう！　とりあえず、冒頭にも言ったけど、ゆるふわ.rb 行ってみたい。あと、船乗りたいよね、船。来年の春ぐらいまでには実現させたい。</p><p>最後に、わざわざ東京から来てくれた @kirin_nico なのだけど、LT が時間切れになった挙句、帰りの松山空港で半田ごて（？）が手荷物検査で引っかかって収監された<a href="#f-6e30fe8c" name="fn-6e30fe8c" title="まぁ、すぐ解放されたっぽいが">*2</a>とあとで聞いて、とても申し訳なく思っていることを最後に申し添えておく。</p><p><blockquote class="twitter-tweet" lang="ja"><p><a href="https://twitter.com/jz5">@jz5</a> <a href="https://twitter.com/daisuke_nomura">@daisuke_nomura</a> <a href="https://twitter.com/kirin_nico">@kirin_nico</a> きりんさんが連行されたよ……</p>&mdash; 酢酸(さくさん) (@ch3cooh) <a href="https://twitter.com/ch3cooh/statuses/478119843242053633">2014, 6月 15</a></blockquote><script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script></p><p>それではみなさん、また遠くないうちにお会いしましょう。</p>

</div><div class="footnote">
<p class="footnote"><a href="#fn-c6bf52f9" name="f-c6bf52f9" class="footnote-number">*1</a><span class="footnote-delimiter">:</span><span class="footnote-text">@jz5 によって定式化された公式による</span></p>
<p class="footnote"><a href="#fn-6e30fe8c" name="f-6e30fe8c" class="footnote-number">*2</a><span class="footnote-delimiter">:</span><span class="footnote-text">まぁ、すぐ解放されたっぽいが</span></p>
</div>