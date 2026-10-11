# わーすた楽曲ソート

非公式ファンサイト。93曲、初期表示92曲。公式MV・ダンス・ライブ等へのリンク66曲。

曲の選択・検索・年代フィルター・上位件数指定・自動保存・戻る・ジャケット入りPNG・テキスト／共有リンクのコピーに対応。

## 起動

Node.js 20.9以上で `npm start`。http://127.0.0.1:4187/ を開きます。通常起動にパッケージのインストールは不要です。

## 曲目の方針と出典

[わーすた公式ディスコグラフィー](https://wa-suta.world/discography/)、Apple Musicの各作品曲目、公式YouTube（現行・avex時代）、公式コラボ告知。

SE、インスト、カラオケ、メンバー個人ソロは除外。同曲の再録・短縮版は原曲へ統合。リミックス・別言語版は該当曲があるときだけチェックボックスを表示し、初期オフです。スペイン語コラボ版「Yo Quiero Vivir（Wasuta × Adexe y Nau）」は別言語版チェックボックスで切替（初期オフ）。日本語版は通常収録。DVDのグループ公演曲目にある初期の5曲も収録。ソロのカバー映像はグループの動画として使用しません。

`dateKind: live` の日付は資料で確認できた公演日で、初披露日や発売日ではありません。音源未確認のライブ曲には無関係なジャケットを流用せず、曲名を表示します。曲別の出典は songs.js に保存。

## 確認記録

確認日 2026-10-11。公式YouTube公開一覧414本を取得し、選別した129本のプレイヤーメタデータを照合しました。短尺・トーク等は公開タイトルで分類しています。映像全編の視聴や非公開曲を含む網羅性の保証ではありません。

「ミラクルマジカルヘルシーパワー」MVはnosh公式告知のURLを採用。プレイヤー取得はHTTP429のため、再生可否は未確認。

採否と統合先は catalog-audit.json と 楽曲確認台帳.md、動画の対応表は 動画確認一覧.md に記録しています。

## 検証・保守

`npm run check`、`npm test`。公開ファイルはこのフォルダーのみで動作します。調査キャッシュ・認証情報・node_modulesは公開しません。

保守用ルートで `node scripts/collect-wasuta-anthurium.mjs` → `node scripts/build-wasuta-anthurium.mjs` → `node scripts/audit-wasuta-anthurium.mjs` → `node scripts/package-new-covers.mjs わーすた楽曲ソート` → `node scripts/finish-wasuta-anthurium.mjs`。追加候補の判断は scripts/wasuta-supplemental.json に保持。再調査ではキャッシュを更新し、未一致候補の採否を確認してください。
