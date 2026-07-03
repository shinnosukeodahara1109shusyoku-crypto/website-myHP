# 案件スターターテンプレート（POP・青×白）

新しいウェブ制作案件を素早く立ち上げるための雛形です。
レスポンシブ対応・お問い合わせフォーム・OGP・favicon・プレビュー設定を最初から含んでいます。

現在のデザインは「ポップ・青×白」トーン（参考：PLAZA風）。
マーキー（流れる文字）・丸みのあるカード・黄色/ピンクの差し色などの演出入り。
別の雰囲気にしたいときは `css/style.css` の `:root` の色とフォントを変えるだけでOK。

## 使い方（新しい案件を始めるとき）

### 1. フォルダを複製してリネーム
このフォルダごとコピーし、案件名に変える。
例：`001_〇〇カフェ_LP`

### 2. そのフォルダで新しいClaude Codeセッションを開く
案件ごとにセッション（＝作業フォルダ）を分けると、文脈・メモリ・Gitが混ざらない。

### 3. 雰囲気を変える（一番効くところ）
`css/style.css` の先頭 `:root` にある色とフォントを変えるだけで、全体の印象が変わる。
- `--color-accent` … アクセント色（ボタン等）
- `--color-dark` / `--color-bg` … 背景の基調
- `--font-base` … フォント（明朝にしたいなら serif 系に）

### 4. 中身を差し替える
`index.html` の `TODO` コメントと、`BRAND` / 見出し / 本文を案件用に書き換える。
画像は `assets/` に入れて `<img>` で読み込む（Web用に圧縮しておくと軽い）。

### 5. お問い合わせフォームを設定
`index.html` の CONTACT のコメント参照。Googleフォーム連携 or Formspree。

### 6. 公開（静的サイトの定番フロー）
1. `git init` → GitHubに新規リポジトリを作成 → push
2. Netlify で「Import an existing project」→ そのリポジトリを選択 → Deploy
3. 発行された本番URLで、OGPの `REPLACE.example.com` を差し替えて再push
4. 検索に載せたい場合のみ Google Search Console に登録＋sitemap送信
   - 逆に「リンク限定で検索に出したくない」場合は `<meta name="robots" content="noindex">` と robots.txt の `Disallow: /`

## プレビュー（ローカル確認）
このフォルダで Claude Code の preview を使うと、`.claude/serve.js`（Node標準のみ）で
`http://localhost:8080` に配信される。ポートを変えたいときは launch.json と serve.js を編集。

## 含まれるファイル
```
index.html          … 本体（ヘッダー/ヒーロー/About/Services/Works/Contact/フッター）
css/style.css       … スタイル（:root で一括テーマ変更）
assets/favicon.svg  … 差し替え用の簡易ファビコン
robots.txt          … クローラー設定（初期は許可）
sitemap.xml         … サイトマップ（URL差し替えて使う）
.gitignore          … OS/エディタの不要ファイルを除外
.claude/            … プレビュー用の設定（テンプレートとして引き継ぐため同梱）
```

## このテンプレートの使い方（GitHubテンプレートリポジトリ）
このリポジトリはGitHubの「テンプレートリポジトリ」に設定してあります。
新しい案件を始めるときは、GitHubでこのリポジトリの **「Use this template」** ボタンから
新しいリポジトリを作成 → それを Claude（Web版／デスクトップ版どちらでも）で開いて制作を開始します。
- Web版：新リポジトリを選んで開始
- デスクトップ版：新リポジトリをクローン、またはこのフォルダをコピー

※ `.claude/` は公開サイトにも含まれますが、中身は開発用サーバーの設定だけで機密情報はありません。
　気になる場合はデプロイ前に `.gitignore` へ `.claude/` を追記してください。
