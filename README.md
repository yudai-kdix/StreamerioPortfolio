# Streamerio Slides + Developer Intro

Vue 3 (Vite) 製の1ページサイトです。上部にFigma Slidesの埋め込み、下部に開発者カードの一覧を表示します。Vercelにデプロイできます。

## セットアップ

```bash
cd app
cp .env.example .env # 必要に応じてURLを編集
npm install
npm run dev
```

## 環境変数

- `VITE_FIGMA_SLIDE_URL` — Figma Slidesの埋め込みURL
- `VITE_UNITYROOM_URL` — unityroomのゲームURL（ヘッダーのボタンで使用）
  - 未設定（`.env`が無い/空）でも `https://unityroom.com/games/streamerio` を既定で使用します。

## 構成

```
app/
  index.html
  src/
    App.vue
    main.js
    styles.css
    config.ts
    components/
      AppHeader.vue
      SlideEmbed.vue
      DeveloperList.vue
      DeveloperCard.vue
      AppFooter.vue
    data/
      developers.js
  vite.config.ts
  package.json
  vercel.json
```

## 編集ポイント

- 開発者カードのデータ: `app/developer.json`（JSONに変更）
- unityroomリンク: `.env` の `VITE_UNITYROOM_URL`
- スタイル（ダーク + ピクセル風）: `src/styles.css`
- アイコン: `lucide-vue-next` を使用（X/外部リンク/ゲームパッド）

### `developer.json` スキーマ例

```json
[
  {
    "icon": "/icons/sample1.png",
    "name": "お名前",
    "roles": ["ゲームロジック", "UI/UX"],
    "bio": "ひとことコメントをここに。",
    "xUrl": "https://x.com/your_handle",
    "portfolioUrl": "https://your-portfolio.example.com"
  }
]
```

アイコン画像を使う場合は `app/public/icons/` に配置し、JSONでは `"/icons/xxx.png"` のようにルート相対で指定してください。

## デプロイ（Vercel）

1. このリポジトリをGitHubにプッシュ
2. VercelでNew Project → 対象リポジトリを選択
3. Framework: Vite（自動検出）
4. Build Command: `vite build`（または `npm run build`）
5. Output Directory: `dist`
6. 必要なら Environment Variables を追加（`VITE_*`）

## ライセンス

プロジェクト固有のライセンスに従ってください。
