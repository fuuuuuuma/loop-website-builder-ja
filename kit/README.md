# codex-web-builder-ja — ループで完璧なWebサイトを作る Codexキット

> **これは何**：Codex に渡すと、**いきなり作らず「壁打ち」から始まり**、`/goal` ループと
> **サブエージェント採点**で「各観点100点」になるまで作り込み、**ボタンの押した先まで動く**Webサイトを、
> **公開まで**面倒みる配布キット（プレゼント）です。ランタイムは **Codex デスクトップアプリ**（内蔵 GPT Image 2.0・APIキー不要）。

このキットは、YouTube「AIエージェントチャンネル」の解説回
**「ループエンジニアリングで完璧なWebサイトを1発生成」** の配布物です。

---

## 3行でわかる

- **1発で完璧は狙わない。** 「合格の定義」と「採点役（サブエージェント）」を用意して**ループ**で仕上げる。
- **側だけ作らない。** 全ボタン・全リンク・全フォームの「押した先」まで動かす。
- **Simple is the best。** 目的1つ・CTA1つに絞る。要素を足しすぎない。

---

## 使い方（3ステップ）

1. **開く**：Codex デスクトップアプリ（ChatGPT アカウント）で、このフォルダを**プロジェクトとして開く**。
   Codex が `AGENTS.md` を自動で読む。
2. **話しかける**：「**サイト作って**」。いきなり作らず、**壁打ち（一問一答）** が始まり `site-spec.md` が固まる。
3. **送る**：`prompts/goal-loop.md` の `/goal …` を自分で送る。3体以上のサブエージェントが各観点100点まで回し、
   最後に **GitHub Pages / Vercel** を聞いて**公開**する。

> 接続（画像生成・デプロイ）は [`reference/connections.md`](reference/connections.md)。

---

## 4フェーズ

```
① 壁打ち(site-grilling) → ② /goalループ(goal-loop) → ③ サイト生成(site-builder) → ④ デプロイ(人間確認後)
   仕様を固める            各観点100点まで自走          機能する導線まで作る        GitHub/Vercel
```

---

## 収録物

| パス | 中身 |
|---|---|
| `AGENTS.md` | Codex が自動で読む背骨（黄金ルール・4フェーズ） |
| `skills/site-grilling/` | 壁打ち（GrillMe 方式・一問一答）＋ `references/question-bank.md` |
| `skills/site-builder/` | サイト生成（機能する導線まで）＋ `references/qa-checklist.md`・`shareable-prompts.md` |
| `prompts/goal-loop.md` | `/goal` 契約＋closed ループ（各観点100点まで自走） |
| `design-systems/` | **DESIGN.md 30選**（配色・フォント・型の正典。1枚選んで `:root` 固定） |
| `reference/loops.md` | ループ入門（なぜループ／`/goal`／検証ゲート） |
| `reference/site-playbook.md` | サイト作りのコツ（構成・CTA・「側だけダメ」・Simple is best） |
| `reference/components.md` | コンポーネントの種類（Material 3 準拠の部品辞書） |
| `reference/graphics-animation.md` | グラフィック/アニメ/機能の**名称とプロンプト** |
| `reference/reference-sites.md` | 参考Webサイト集（トンマナの当て先） |
| `reference/connections.md` | 接続（GPT Image 2.0・GitHub/Vercel） |
| `CREDITS.md` / `LICENSE` | 謝辞（GrillMe・goal-setter・makeloop・Loops記事）／ MIT |

---

## 由来・ライセンス

壁打ちは **GrillMe / grilling**（MIT・Matt Pocock）、ループは **goal-setter / makeloop**（MIT）と
Anthropic の [Getting Started with Loops](https://claude.com/blog/getting-started-with-loops) 由来。
くわしくは [CREDITS.md](CREDITS.md)。本キットは **MIT**（[LICENSE](LICENSE)）—— 自由に使い・改変し・配ってOK。原典表示だけ残してください。
