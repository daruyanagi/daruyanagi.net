---
date: 2015-09-15T18:31:48.0000000
draft: false
title: "Windows のあのフォルダーをサクッと開きたい！　覚えておくとちょっと便利なシェルコマンド"
tags: []
eyecatch: 20150915175559.png
---
<p><span itemscope itemtype="http://schema.org/Photograph"><img src="20150915175559.png" alt="f:id:daruyanagi:20150915175559p:plain" title="f:id:daruyanagi:20150915175559p:plain" class="hatena-fotolife" itemprop="image"></span></p><p>ちょっと覚えておくと便利なシェルコマンドの一覧。たとえば［Windows］＋［R］キーで「ファイルを指名して実行」を開いて、著ちょいと入力してエンターを押すと目当てのフォルダーへサクッとアクセスできる。OS起動時に実行開始するアプリを登録する“shell:Startup”辺りは割と使うかな？</p>

<table>
<tr>
<td>shell:AccountPictures	</td>
<td>“アカウントの画像”フォルダー</td>
</tr>
<tr>
<td>shell:AddNewProgramsFolder	</td>
<td>「コントロール パネル」の“プログラムの取得”</td>
</tr>
<tr>
<td>shell:Administrative Tools	</td>
<td>“プログラム\管理ツール”フォルダー</td>
</tr>
<tr>
<td>shell:AppData	</td>
<td>C:\Users\<username>\AppData\Roaming</td>
</tr>
<tr>
<td>shell:Application Shortcuts	</td>
<td>\AppData\Local\Microsoft\Windows<br>\Application Shortcuts</td>
</tr>
<tr>
<td>shell:AppsFolder	</td>
<td>モダンアプリを集めた仮想フォルダー“Applications”</td>
</tr>
<tr>
<td>shell:AppUpdatesFolder	</td>
<td>「コントロール パネル」の“インストールされた更新プログラム”</td>
</tr>
<tr>
<td>shell:Cache	</td>
<td>「Internet Explorer」のキャッシュフォルダー</td>
</tr>
<tr>
<td>shell:Camera Roll	</td>
<td>　</td>
</tr>
<tr>
<td>shell:CD Burning	</td>
<td>CDを焼くときに使う“一時書き込みフォルダー”</td>
</tr>
<tr>
<td>shell:ChangeRemoveProgramsFolder	</td>
<td>「コントロール パネル」の“プログラムと機能”</td>
</tr>
<tr>
<td>shell:Common Administrative Tools	</td>
<td>“プログラム\管理ツール”フォルダー（すべてのユーザー）</td>
</tr>
<tr>
<td>shell:Common AppData	</td>
<td>C:\ProgramData</td>
</tr>
<tr>
<td>shell:Common Desktop	</td>
<td>“デスクトップ”（すべてのユーザー）</td>
</tr>
<tr>
<td>shell:Common Documents	</td>
<td>“ドキュメント”（すべてのユーザー）</td>
</tr>
<tr>
<td>shell:Common Programs	</td>
<td>“スタート メニュー\プログラム”（すべてのユーザー）</td>
</tr>
<tr>
<td>shell:Common Start Menu	</td>
<td>“スタート メニュー”（すべてのユーザー）</td>
</tr>
<tr>
<td>shell:Common Startup	</td>
<td>“スタートアップ”（すべてのユーザー）</td>
</tr>
<tr>
<td>shell:Common Templates	</td>
<td>“Templates”（すべてのユーザー）</td>
</tr>
<tr>
<td>shell:CommonDownloads	</td>
<td>“ダウンロード”（すべてのユーザー）</td>
</tr>
<tr>
<td>shell:CommonMusic	</td>
<td>“ミュージック”（すべてのユーザー）</td>
</tr>
<tr>
<td>shell:CommonPictures	</td>
<td>“ピクチャー”（すべてのユーザー）</td>
</tr>
<tr>
<td>shell:CommonRingtones	</td>
<td>“Ringtones”（すべてのユーザー）</td>
</tr>
<tr>
<td>shell:CommonVideo	</td>
<td>“ビデオ”（すべてのユーザー）</td>
</tr>
<tr>
<td>shell:ConflictFolder	</td>
<td>「コントロール パネル」の“競合”</td>
</tr>
<tr>
<td>shell:ConnectionsFolder	</td>
<td>「コントロール パネル」の“ネットワーク接続”</td>
</tr>
<tr>
<td>shell:Contacts	</td>
<td>“アドレス帳”</td>
</tr>
<tr>
<td>shell:ControlPanelFolder	</td>
<td>「コントロール パネル」の“すべてのコントロール パネル項目”</td>
</tr>
<tr>
<td>shell:Cookies	</td>
<td>「Internet Explorer」のCookieフォルダー</td>
</tr>
<tr>
<td>shell:CredentialManager	</td>
<td>\AppData\Roaming\Microsoft\Credentials</td>
</tr>
<tr>
<td>shell:CryptoKeys	</td>
<td>\AppData\Roaming\Microsoft\Crypto</td>
</tr>
<tr>
<td>shell:CSCFolder	</td>
<td>　</td>
</tr>
<tr>
<td>shell:Desktop	</td>
<td>“デスクトップ”</td>
</tr>
<tr>
<td>shell:Device Metadata Store	</td>
<td>C:\ProgramData\Microsoft\ Windows<br>\DeviceMetadataStore</td>
</tr>
<tr>
<td>shell:DocumentsLibrary	</td>
<td>“ドキュメント”ライブラリ</td>
</tr>
<tr>
<td>shell:Downloads	</td>
<td>“ダウンロード”</td>
</tr>
<tr>
<td>shell:DpapiKeys	</td>
<td>>\AppData\Roaming\Microsoft\Protect</td>
</tr>
<tr>
<td>shell:Favorites	</td>
<td>“お気に入り”</td>
</tr>
<tr>
<td>shell:Fonts	</td>
<td>C:\Windows\Fonts</td>
</tr>
<tr>
<td>shell:Games	</td>
<td>“ゲーム”</td>
</tr>
<tr>
<td>shell:GameTasks	</td>
<td>\AppData\Local\Microsoft\Windows<br>\GameExplorer</td>
</tr>
<tr>
<td>shell:History	</td>
<td>\AppData\Local\Microsoft\Windows\History</td>
</tr>
<tr>
<td>shell:HomeGroupCurrentUserFolder	</td>
<td>The Home Group folder for the current user</td>
</tr>
<tr>
<td>shell:HomeGroupFolder	</td>
<td>The Home Group root folder</td>
</tr>
<tr>
<td>shell:ImplicitAppShortcuts	</td>
<td>\AppData\Roaming\Microsoft\Internet Explorer\Quick Launch\User Pinned\ImplicitAppShortcuts</td>
</tr>
<tr>
<td>shell:InternetFolder	</td>
<td>「Internet Explorer」の起動</td>
</tr>
<tr>
<td>shell:Libraries	</td>
<td>ライブラリ</td>
</tr>
<tr>
<td>shell:Links	</td>
<td>“リンク”（「エクスプローラー」のナビゲーションペインに表示される）</td>
</tr>
<tr>
<td>shell:Local AppData	</td>
<td>C:\Users\<username>\AppData\Local</td>
</tr>
<tr>
<td>shell:LocalAppDataLow	</td>
<td>C:\Users\<username>\AppData\LocalLow</td>
</tr>
<tr>
<td>shell:LocalizedResourcesDir	</td>
<td>　</td>
</tr>
<tr>
<td>shell:MAPIFolder	</td>
<td>「Microsoft Outlook」のフォルダーらしい（入れてないから知らん）</td>
</tr>
<tr>
<td>shell:MusicLibrary	</td>
<td>“ミュージック”ライブラリ</td>
</tr>
<tr>
<td>shell:My Music	</td>
<td>“ミュージック”フォルダー</td>
</tr>
<tr>
<td>shell:My Pictures	</td>
<td>“ピクチャー”フォルダー</td>
</tr>
<tr>
<td>shell:My Video	</td>
<td>“ビデオ”フォルダー</td>
</tr>
<tr>
<td>shell:MyComputerFolder	</td>
<td>“PC”</td>
</tr>
<tr>
<td>shell:NetHood	</td>
<td>\AppData\Roaming\Microsoft\Windows<br>\Network Shortcuts</td>
</tr>
<tr>
<td>shell:NetworkPlacesFolder	</td>
<td>“ネットワーク”</td>
</tr>
<tr>
<td>shell:OEM Links	</td>
<td>　</td>
</tr>
<tr>
<td>shell:Original Images	</td>
<td>　</td>
</tr>
<tr>
<td>shell:Personal	</td>
<td>“ドキュメント”フォルダー</td>
</tr>
<tr>
<td>shell:PhotoAlbums	</td>
<td>　</td>
</tr>
<tr>
<td>shell:PicturesLibrary	</td>
<td>“ピクチャー”ライブラリ</td>
</tr>
<tr>
<td>shell:Playlists	</td>
<td>　</td>
</tr>
<tr>
<td>shell:PrintersFolder	</td>
<td>\AppData\Roaming\Microsoft\Windows<br>\Printer Shortcuts</td>
</tr>
<tr>
<td>shell:PrintHood	</td>
<td>\AppData\Roaming\Microsoft\Windows<br>\Printer Shortcuts</td>
</tr>
<tr>
<td>shell:Profile	</td>
<td>ユーザーフォルダー</td>
</tr>
<tr>
<td>shell:ProgramFiles	</td>
<td>C:\Program Files</td>
</tr>
<tr>
<td>shell:ProgramFilesCommon	</td>
<td>C:\Program Files\Common Files</td>
</tr>
<tr>
<td>shell:ProgramFilesCommonX64	</td>
<td>C:\Program Files\Common Files</td>
</tr>
<tr>
<td>shell:ProgramFilesCommonX86	</td>
<td>C:\Program Files (x86)\Common Files</td>
</tr>
<tr>
<td>shell:ProgramFilesX64	</td>
<td>C:\Program Files</td>
</tr>
<tr>
<td>shell:ProgramFilesX86	</td>
<td>C:\Program Files (x86)</td>
</tr>
<tr>
<td>shell:Programs	</td>
<td>\AppData\Roaming\Microsoft\Windows<br>\Start Menu\Programs</td>
</tr>
<tr>
<td>shell:Public	</td>
<td>C:\Users\Public</td>
</tr>
<tr>
<td>shell:PublicAccountPictures	</td>
<td>C:\Users\Public\AccountPictures</td>
</tr>
<tr>
<td>shell:PublicGameTasks	</td>
<td>C:\ProgramData\Microsoft\Windows<br>\GameExplorer</td>
</tr>
<tr>
<td>shell:PublicLibraries	</td>
<td>C:\Users\Public\Libraries</td>
</tr>
<tr>
<td>shell:Quick Launch	</td>
<td>>\AppData\Roaming\Microsoft\Internet Explorer\Quick Launch</td>
</tr>
<tr>
<td>shell:Recent	</td>
<td>“最近使った項目”</td>
</tr>
<tr>
<td>shell:RecordedTVLibrary	</td>
<td>　</td>
</tr>
<tr>
<td>shell:RecycleBinFolder	</td>
<td>“ごみ箱”</td>
</tr>
<tr>
<td>shell:ResourceDir	</td>
<td>C:\Windows\Resources（Windows テーマの保存場所）</td>
</tr>
<tr>
<td>shell:Ringtones	</td>
<td>\AppData\Local\Microsoft\Windows<br>\Ringtones</td>
</tr>
<tr>
<td>shell:Roamed Tile Images	</td>
<td>　</td>
</tr>
<tr>
<td>shell:Roaming Tiles	</td>
<td>\AppData\Local\Microsoft\Windows<br>\RoamingTiles</td>
</tr>
<tr>
<td>shell:SavedGames	</td>
<td>“保存したゲーム”</td>
</tr>
<tr>
<td>shell:Screenshots	</td>
<td>［Windows］＋［Print Screen］キーで撮影したスクリーンショットの保存先</td>
</tr>
<tr>
<td>shell:Searches	</td>
<td>“検索”</td>
</tr>
<tr>
<td>shell:SearchHistoryFolder	</td>
<td>\AppData\Local\Microsoft\Windows<br>\ConnectedSearch\History</td>
</tr>
<tr>
<td>shell:SearchHomeFolder	</td>
<td>“検索結果”</td>
</tr>
<tr>
<td>shell:SearchTemplatesFolder	</td>
<td>　</td>
</tr>
<tr>
<td>shell:SendTo	</td>
<td>“送る”メニューに表示されるショートカットを保存するフォルダー</td>
</tr>
<tr>
<td>shell:SkyDrive	</td>
<td>現在は shell:OneDrive。当然ながら“OneDrive”フォルダーを表示</td>
</tr>
<tr>
<td>shell:SkyDriveCameraRoll	</td>
<td>　</td>
</tr>
<tr>
<td>shell:SkyDriveDocuments	</td>
<td>　</td>
</tr>
<tr>
<td>shell:SkyDrivePictures	</td>
<td>　</td>
</tr>
<tr>
<td>shell:Start Menu	</td>
<td>\AppData\Roaming\Microsoft\Windows<br>\Start Menu</td>
</tr>
<tr>
<td>shell:Startup	</td>
<td>“スタートアップ”</td>
</tr>
<tr>
<td>shell:SyncCenterFolder	</td>
<td>　</td>
</tr>
<tr>
<td>shell:SyncResultsFolder	</td>
<td>「コントロール パネル」の“同期結果”</td>
</tr>
<tr>
<td>shell:SyncSetupFolder	</td>
<td>「コントロール パネル」の“同期のセットアップ”</td>
</tr>
<tr>
<td>shell:System	</td>
<td>C:\Windows\System32</td>
</tr>
<tr>
<td>shell:SystemCertificates	</td>
<td>\AppData\Roaming\Microsoft<br>\SystemCertificates</td>
</tr>
<tr>
<td>shell:SystemX86	</td>
<td>C:\Windows\SysWOW64</td>
</tr>
<tr>
<td>shell:Templates	</td>
<td>\AppData\Roaming\Microsoft\Windows<br>\Templates</td>
</tr>
<tr>
<td>shell:ThisPCDesktopFolder	</td>
<td>“デスクトップ”</td>
</tr>
<tr>
<td>shell:User Pinned	</td>
<td>\AppData\Roaming\Microsoft\Internet Explorer\Quick Launch\User Pinned</td>
</tr>
<tr>
<td>shell:UserProfiles	</td>
<td>C:\Users</td>
</tr>
<tr>
<td>shell:UserProgramFiles	</td>
<td>\AppData\Local\Programs</td>
</tr>
<tr>
<td>shell:UserProgramFilesCommon	</td>
<td>\AppData\Local\Programs\Common</td>
</tr>
<tr>
<td>shell:UsersFilesFolder	</td>
<td>ユーザーフォルダー</td>
</tr>
<tr>
<td>shell:UsersLibrariesFolder	</td>
<td>ライブラリ</td>
</tr>
<tr>
<td>shell:VideosLibrary	</td>
<td>“ビデオ”ライブラリ</td>
</tr>
<tr>
<td>shell:Windows	</td>
<td>C:\Windows</td>
</tr>
</table><p>ここに挙げたのは Windows 8.1 世代のモノなので、Windows 10 では追加や廃止があるかも。</p><p>単語の間に空白があったりなかったりと命名規則が統一されていないのは Microsoft らしいなぁ、と思います。</p><p><iframe src="//hatenablog-parts.com/embed?url=http%3A%2F%2Fwinaero.com%2Fblog%2Fshell-commands-in-windows-8-1%2F" title="Shell commands in Windows 8.1" class="embed-card embed-webcard" scrolling="no" frameborder="0" style="display: block; width: 100%; height: 155px; max-width: 500px; margin: 10px 0px;"></iframe></p>
