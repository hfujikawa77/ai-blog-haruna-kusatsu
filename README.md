# はるな・草津！群馬の自然と温泉ノート

> 榛名山・草津温泉エリアの家族旅行情報ブログ - AI アシストによるコンテンツ制作プロジェクト

![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-active-brightgreen)
![Jekyll](https://img.shields.io/badge/Jekyll-Minima-red)

**ライブサイト**: [https://hfujikawa77.github.io/ai-blog-haruna-kusatsu/](https://hfujikawa77.github.io/ai-blog-haruna-kusatsu/)

---

## 概要

榛名山・伊香保温泉・草津温泉エリアを家族で楽しむための旅行情報ブログです。

AI を活用したコンテンツ制作により、高品質な記事を定期的に公開しています。

### 主な特徴

- **定期更新される記事** - 榛名山・草津温泉エリアのテーマを網羅
- **4コママンガ風イラスト** - ChatGPT, Gemini で生成した視覚的なコンテンツ
- **音声解説** - NotebookLM による記事の読み上げ音声
- **インタラクティブなクイズ** - 記事の理解度を確認できるクイズ
- **厳選された YouTube 動画** - 各記事に関連動画を掲載
- **体験ミッション** - 子どもたちが実際に取り組める課題

---

## 技術スタック

| カテゴリ | 技術 |
|---------|------|
| **ホスティング** | GitHub Pages |
| **静的サイトジェネレーター** | Jekyll (Minima テーマ) |
| **コンテンツ生成** | Claude Code |
| **イラスト生成** | ChatGPT, Gemini |
| **音声生成** | NotebookLM |
| **バージョン管理** | Git / GitHub |

---

## セットアップ方法

### GitHub Pages の設定手順

1. **リポジトリのフォークまたはクローン**
   ```bash
   git clone https://github.com/hfujikawa77/ai-blog-haruna-kusatsu.git
   cd ai-blog-haruna-kusatsu
   ```

2. **GitHub リポジトリの Pages 設定**
   - GitHub リポジトリページにアクセス
   - `Settings` → `Pages` を選択
   - `Source` を `main` ブランチに設定

3. **`_config.yml` の確認**
   ```yaml
   title: はるな・草津！群馬の自然と温泉ノート
   baseurl: "/ai-blog-haruna-kusatsu"
   theme: minima
   timezone: Asia/Tokyo
   future: true
   ```

4. **変更をコミット&プッシュ**
   ```bash
   git add _config.yml
   git commit -m "Update configuration"
   git push origin main
   ```

---

## プロジェクト構成

```
ai-blog-haruna-kusatsu/
├── _config.yml           # Jekyll 設定ファイル
├── _posts/               # 記事の Markdown ファイル
│   └── YYYY-MM-DD-title.md
├── _sns/                 # SNS 投稿用文章
│   └── YYYY-MM-DD/
│       ├── twitter.md
│       ├── facebook.md
│       └── instagram.md
├── assets/               # 画像・音声ファイル
│   ├── YYYY-MM-DD-comic.png
│   └── YYYY-MM-DD-sound.mp3
├── _scripts/
│   └── gen-article.sh    # 記事・SNS自動生成スクリプト
├── prompts/              # Claude Code 用プロンプト
│   ├── new-article.md
│   ├── new-sns.md
│   └── fix-video.md
├── instruction.md        # 執筆要領と掲載予定カレンダー
├── index.md              # トップページ
└── README.md             # このファイル
```

---

## 運用方法（日々の記事作成フロー）

### 自動生成スクリプト

```bash
# 今日の記事を生成
./_scripts/gen-article.sh

# 特定日付の記事を生成
./_scripts/gen-article.sh 2026-04-29

# 強制再生成
./_scripts/gen-article.sh 2026-04-29 -f
```

### 手動フロー

1. **記事生成** → `prompts/new-article.md` を Claude Code に送信
2. **イラスト生成** → ChatGPT/Gemini で `assets/YYYY-MM-DD-comic.png` を作成
3. **音声生成** → NotebookLM で `assets/YYYY-MM-DD-sound.mp3` を作成
4. **SNS投稿文生成** → `prompts/new-sns.md` を Claude Code に送信
5. **公開** → `git commit & push`
