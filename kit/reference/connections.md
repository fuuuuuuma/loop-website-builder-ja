# 接続ガイド — connections（Codex デスクトップアプリ前提）

このキットは **Codex デスクトップアプリ**で使う前提。サイトを作り始める前に、
(1) キットの渡し方、(2) 画像生成、(3) デプロイ の接続だけ確認しておく。
**APIキーは不要**（アプリは ChatGPT アカウントで動く。大量生成のときだけ任意で API）。出典は末尾。

---

## 0. キットの渡し方（デスクトップアプリ）
- Codex アプリ（ChatGPT アカウントでサインイン）で、このフォルダ（リポジトリ）を **プロジェクトとして開く**。
- Codex は**作業前にプロジェクト直下の `AGENTS.md` を自動で読む**（読込順: `~/.codex` → プロジェクトルート → 作業ディレクトリ）。
- スレッドで「サイト作って」と話しかけると、`AGENTS.md` に従って**プランモードで壁打ち**から始まる。

---

## 1. 画像生成（GPT Image 2.0・内蔵）
Codex アプリは**画像生成を内蔵**している。スレッドで「背景画像を作って」と頼むだけで **GPT Image 2.0（`gpt-image-2`）** が使える。

| 方法 | 接続 | 向いている場面 |
|---|---|---|
| **A. アプリ内蔵（推奨・既定／APIキー不要）** | ChatGPT アカウントでサインイン済みなら**追加設定なし**。内蔵の画像生成が `gpt-image-2` を使う | まずこれ。少〜中量 |
| **B. OpenAI Developers API** | `OPENAI_API_KEY` を設定し `v1/images/generations` で `gpt-image-2` を呼ぶ（API 課金） | 大量生成・課金を分けたい |
| **C. Runway MCP コネクタ** | アプリ設定から `https://mcp.runwayml.com/mcp` を接続。別モデル・動画も | 別モデルが要るとき |
| **D. HiggsField MCP コネクタ** | アプリ設定から HiggsField の MCP を接続 | コネクタ運用の代替 |

> ※ 2026/4/16 時点の内蔵既定は `gpt-image-1.5`、4/21 の `gpt-image-2` で更新。新しい方（GPT Image 2.0）を使う。

用途: **ヒーロー背景・装飾・写真・OG画像・アイコン**。**重要テキストは焼き込まず HTML** に置く（編集・SEO・崩れ対策）。

---

## 2. コネクタ／プラグインの追加（アプリの設定から）
- **Codex アプリ左下の設定アイコン → MCP Servers → Add servers → Streamable HTTP** に接続先 URL を入れて認証する。
- プラグイン（スキル＋コネクタ＋MCP の束）も同様にアプリから追加でき、**アプリ／CLI／VS Code 拡張で共通**に使える。

---

## 3. デプロイ（GitHub Pages か Vercel）
静的サイトは **GitHub Pages** か **Vercel**。**プラグイン／コネクタを接続しておくと、Codex から公開まで進められる。**

| 先 | 接続（推奨） | 向いている場面 |
|---|---|---|
| **GitHub Pages（無料・シンプル）** | GitHub リポジトリに push → Pages を有効化（`gh`／git） | 完全無料・静的で十分なとき |
| **Vercel（プラグインで公開）** | アプリから **Vercel プラグイン／MCP** を接続 → 「create a deployment」でプレビュー公開（または `vercel` CLI） | プレビューURL・独自ドメイン・表示が速い |

**公開（デプロイ）＝取り消せない外部公開**なので、実行は **必ず人間が確認してから**（自動で公開しない）。
公開後は本番 URL が HTTP 200 を返すこと・**本番でも全導線が動くこと**・計測タグが発火することを確認する。

---

## まとめ（最短ルート）
1. **渡す**: Codex アプリでこのフォルダを開く →「サイト作って」。
2. **壁打ち→ループ**: 仕様を固め、`/goal` で各観点100点まで自走。
3. **画像**: 内蔵 GPT Image 2.0（APIキー不要）。**デプロイ**: GitHub Pages か Vercel → 人間確認して公開。

---

## 出典
- Introducing the Codex app｜OpenAI — https://openai.com/index/introducing-the-codex-app/
- Codex app / Features（プロジェクト単位・内蔵画像生成）｜OpenAI Developers — https://developers.openai.com/codex/app/features
- Custom instructions with AGENTS.md（読込順）｜OpenAI Developers — https://developers.openai.com/codex/guides/agents-md
- Introducing gpt-image-2（API と Codex で利用可）｜OpenAI Developer Community — https://community.openai.com/t/introducing-gpt-image-2-available-today-in-the-api-and-codex/1379479
- Use Vercel's MCP server / Deploy an app or website｜Vercel — https://vercel.com/docs/agent-resources/vercel-mcp
- GitHub Pages ドキュメント — https://docs.github.com/pages
