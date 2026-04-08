# Credify デプロイ手順（5分でURL取得）

## 必要なもの
- GitHubアカウント（無料）→ https://github.com
- Netlifyアカウント（無料）→ https://netlify.com
- AnthropicのAPIキー → https://console.anthropic.com

---

## STEP 1：GitHubにファイルをアップロード（3分）

1. https://github.com/new を開く
2. Repository name に `credify-mvp` と入力
3. **Private** を選択（社外秘のため）
4. **Create repository** をクリック
5. 「uploading an existing file」をクリック
6. 以下の3ファイルをドラッグ＆ドロップ：
   - `index.html`
   - `netlify.toml`
   - `netlify/functions/recommend.js`（フォルダごと）
7. **Commit changes** をクリック

---

## STEP 2：NetlifyでデプロイしてURLを取得（1分）

1. https://netlify.com にアクセスしてログイン
2. **Add new site** → **Import an existing project** をクリック
3. **GitHub** を選択 → `credify-mvp` を選択
4. Build settings はそのままで **Deploy site** をクリック
5. 数秒後に `https://xxxxxx.netlify.app` のURLが発行される ✅

---

## STEP 3：APIキーを設定する（1分）

AIの受講提案機能を使うために必要です。

1. Netlifyのサイト管理画面を開く
2. **Site configuration** → **Environment variables** を開く
3. **Add a variable** をクリック
4. Key: `ANTHROPIC_API_KEY`、Value: あなたのAPIキー を入力
5. **Save** → サイトを **Redeploy**（Deploys → Trigger deploy → Deploy site）

---

## 完了！

```
URL例: https://credify-mvp-xxxxx.netlify.app
```

このURLをブラウザで開けば Credify が動きます。
URLを共有するだけでプレゼン・デモが可能です。

---

## トラブルシューティング

| 症状 | 対処 |
|------|------|
| 受講提案でエラーが出る | STEP 3 でAPIキーが正しく設定されているか確認 |
| ページが表示されない | netlify.toml が正しい場所にあるか確認 |
| 関数が動かない | netlify/functions/recommend.js のパスを確認 |
