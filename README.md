# デジタル化の実験ノート

画像と音を使って、画素・解像度と、デジタル化の3ステップ（標本化・量子化・符号化）をスライダーで体験できるWebページです。

## 機能

- **画像で見る**：解像度（横の画素数）と色の段階（RGB各色のビット数）を変えて、見え方と非圧縮のデータ量を比較
- **音で聞く**：サンプリング周波数と量子化ビット数を変えて、波形・0と1の列・データ量を確認し、実際に音を再生
- プリセット：音楽CD（44.1kHz/16bit）、電話（8kHz/8bit）
- ライト／ダークモード対応、スマホ対応

## ファイル構成

```
index.html      本体（1ファイルで完結）
assets/         差し替え用の素材（任意）
  photo.jpg     使いたい写真
  sound.wav     使いたい音声（短めのモノラル推奨）
.nojekyll       GitHub Pages で Jekyll 処理を無効化
```

`assets/` に素材が無い場合は、内蔵の風景画と合成音声で動きます。

## GitHub Pages での公開手順

1. GitHub で新しいリポジトリを作成（例：`digital-lab-notebook`）
2. このフォルダの中身をすべてアップロード（またはpush）
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/<ユーザー名>/digital-lab-notebook.git
   git push -u origin main
   ```
3. リポジトリの **Settings → Pages** で
   Source を「Deploy from a branch」、Branch を `main` / `/ (root)` にして保存
4. 数分後、`https://<ユーザー名>.github.io/digital-lab-notebook/` で公開されます

## 注意

- `index.html` をローカルでダブルクリックして開くと、ブラウザの制限で `assets/` を読めず代替素材になります。確認は GitHub Pages 上か、`python3 -m http.server` などのローカルサーバーで行ってください。
- フォントは Google Fonts（Zen Kaku Gothic New / Roboto Mono）を読み込んでいます。
