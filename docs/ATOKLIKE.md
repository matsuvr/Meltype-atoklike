# Meltype-atoklike

松VRの個人用カスタマイズ。標準の ATOK キー操作を参考に、Meltype の共通 Core で入力・変換操作を変更した。日英自動判定、Mozc/Zenzai は既存の仕組みを使う。

- 文節幅: 左右、Ctrl+K/L
- 文節移動: Shift+左右、Ctrl+左右で先頭・末尾
- 候補: Space、Shift+Space、変換で次、上で前、Tab/Shift+Tabでページ移動
- 確定: Enter/Ctrl+M、下/Ctrl+Nで部分確定
- 変換取消: Backspace/Ctrl+H、全入力取消: Esc/Ctrl+[
- 後変換: F6〜F10、Ctrl+U/I/O/P/@
- 未入力時: 半角/全角、変換、無変換、F10 で切替（選択文字の再変換を維持）

参照: [ATOK標準キー操作（ジャストシステム）](https://support.justsystems.com/faq/1032/app/servlet/qadoc?QID=040816)

ATOK 固有の辞書セット・電子辞典・連想変換・文字パレット・確定アンドゥ等は別機能。Meltype の入力モデルには未確定読みの任意位置編集がなく、変換前の Ctrl+K/L のカーソル移動、Ctrl+G の前方削除、1音確定は今後の互換課題。Ctrl+左右で端へ移動する操作は変換中が対象。キーの既定値は新規設定に適用される。

## 個人用フォークの運用

- origin は `https://github.com/matsuvr/Meltype-atoklike.git`。上流へのリモートを設定しない。PR・Issue・リリース投稿は上流に対して行わない。
- 上流由来の GitHub Actions、Dependabot、Mergify の設定は削除した。ローカルのビルド手順と原著作者のクレジット・GPL ライセンスは維持する。
- アプリの報告・リリース参照先は個人フォーク。自動更新は新規設定ではオフ、更新のステージングは個人版専用。更新を有効にしても個人フォークのリリースを参照する。
- GitHub の公開フォークは上流のネットワーク上で閲覧できる。完全な非公開管理には、別の非公開独立リポジトリが必要。

## テスト

`dotnet run --project src/Meltype.Core.Tests -- CompositionTests`
