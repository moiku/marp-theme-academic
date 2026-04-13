# marp-theme-academic

[Marp](https://marp.app/) 用の研究発表スライドテーマです。研究室・学会発表・ゼミ発表向けにデザインされています。

| academic-tml | academic-tcue | academic-wsd |
|:---:|:---:|:---:|
| ![](./demo.001.png) | — | — |

---

## テーマ一覧

| テーマ名 | 用途 |
|---|---|
| `academic-tml` | 汎用（長岡技術科学大学カラー） |
| `academic-tcue` | 千葉科学技術大学カラー |
| `academic-wsd` | 早稲田大学カラー |

---

## セットアップ

### 方法 A：VS Code + Marp for VS Code（推奨）

1. VS Code に [Marp for VS Code](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode) をインストール
2. このリポジトリをクローンまたは `themes/` フォルダをダウンロード
3. VS Code の `settings.json` にテーマのパスを追加：

```json
"markdown.marp.themes": [
  "./themes/academic-tml.css"
]
```

### 方法 B：Marp CLI

```bash
marp --theme-set themes/academic-tml.css slide.md
```

または `.marprc.yml` を作成：

```yaml
theme-set:
  - themes/academic-tml.css
```

---

## 基本的な使い方

### Frontmatter（ファイル冒頭に必ず書く）

```markdown
---
marp: true
theme: academic-tml
paginate: true
math: katex
---
```

### スライドの区切り

`---`（水平線）で次のスライドに移動します。

---

## スライド構造

### タイトルスライド

`<!-- _class: lead -->` を付けると背景画像入りのタイトル用レイアウトになります。

```markdown
<!-- _class: lead -->

# 発表タイトル
### サブタイトル

<br>

**氏名**
所属・学年
YYYY/MM/DD
```

### 本文スライド

`# (h1)` がスライド上部のヘッダーバーとして自動的に表示されます。

```markdown
---

# スライドタイトル

## セクション見出し

- ポイント1
- ポイント2
  - 補足

---
```

> **注意**：`<!-- _header: ... -->` は使わないでください。`#` を使うのが新しい方式です。

---

## デザイン要素

### マーカー（蛍光ペン風ハイライト）

```html
<span class="marker">強調したいテキスト</span>
```

### 吹き出しボックス（キーメッセージ）

```html
<div class="bubble">
スライドの結論や重要なメッセージを1つだけ書く
</div>
```

### 2カラムレイアウト

```html
<div class="two-columns">
  <div class="column">
    左カラムの内容
  </div>
  <div class="column">
    右カラムの内容
  </div>
</div>
```

### 脚注

`>` (blockquote) で書くと、スライド下部に小さく固定表示されます。

```markdown
> 1: 参考文献や補足をここに書く
```

### 数式（KaTeX）

```markdown
インライン： $E = mc^2$

ブロック：
$$
\mathcal{L}(\theta) = \frac{1}{n}\sum_{i=1}^{n} \ell(f_\theta(x_i), y_i)
$$
```

数式が大きくてはみ出る場合は `<!-- _class: scale-math -->` を追加してください。

### 画像

```markdown
![w:600 center](./images/figure.png)   <!-- 幅600px・中央寄せ -->
![w:400](./images/figure.png)          <!-- 幅400px・左寄せ -->
![h:300](./images/figure.png)          <!-- 高さ300px -->
```

### パラパラアニメーション（グレーアウト）

前のスライドの要素を薄くして段階的に説明するときに使います。

```html
<span class="dim">前の説明（薄くなる）</span>
<span class="marker">現在の説明（通常表示）</span>
```

---

## カラーパレット（academic-tml）

| 変数名 | カラー | 用途 |
|---|---|---|
| `--color-nut1` | `#3E3A39` | 見出し・本文 |
| `--color-nut2` | `#0A2D92` | ヘッダーバー・強調色 |
| `--color-nut3` | `#A5B8E8` | ボーダー・区切り線 |
| `--color-nut4` | `#FFADB1` | マーカー色 |
| `--color-nut5` | `#E60012` | アクセント赤 |

---

## ライセンス

[MIT License](./LICENSE)
