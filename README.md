# まなびモンスター（通信たいせん版）

小5・小3の姉妹向け学習ゲーム。スマホのホーム画面に追加してアプリとして使う。

## ファイル
| ファイル | 役割 |
|---|---|
| index.html | ゲーム本体 |
| config.js | Firebaseの設定（ここだけ書きかえる） |
| manifest.webmanifest / icon-*.png | ホーム画面アイコン用 |
| database.rules.json | Firebaseのルール（コピー用） |

## 1. Firebase（通信たいせん用・約10分）
1. https://console.firebase.google.com を開き「プロジェクトを作成」→ 名前 `manabi-monster`（アナリティクスはオフでOK）
2. 左メニュー「構築」→「Realtime Database」→「データベースを作成」
   - ロケーション：シンガポール（asia-southeast1）
   - 「テストモードで開始」→ 有効にする
3. 「ルール」タブを開き、`database.rules.json` の中身を貼りつけて「公開」
4. ⚙「プロジェクトの設定」→「マイアプリ」の `</>`（ウェブ）→ アプリ名を入れて登録
5. 表示された `firebaseConfig = { ... }` の `{ ... }` 部分を `config.js` の `null` と置きかえる
   （`databaseURL` が入っていることを確認）

## 2. GitHub Pages（公開）
1. GitHubで新しいリポジトリ `manabi-monster` を作成（Public）
2. 「Add file」→「Upload files」でこのフォルダのファイルを全部ドラッグ＆ドロップ → Commit
3. Settings → Pages → Branch を `main` / `/(root)` にして Save
4. 1〜2分後 `https://<ユーザー名>.github.io/manabi-monster/` で開ける

## 3. スマホに入れる
- iPhone：Safariで開く → 共有ボタン →「ホーム画面に追加」
- Android：Chromeで開く → ︙ →「ホーム画面に追加」

## 遊び方（通信たいせん）
- それぞれのスマホで自分のモンスターを育てる（たまごがかえればOK）
- 「そだてるモンスター」→「べつのスマホとつうしんたいせん」
- 1人が「へやをつくる」→ 4けたのコードを相手に伝える → 相手が入力して「へやにはいる」
- 下の学年が先攻。自分の学年の問題に正解すると攻撃。負けてもEXPがもらえる

## 更新するとき
`index.html` を新しいものに差しかえてアップロードするだけ（`config.js` はそのまま）。
育てたデータは各スマホに保存されているので消えない。
