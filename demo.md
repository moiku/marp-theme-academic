---
marp: true
theme: academic-tml
paginate: true
math: katex
---

<!-- _class: lead -->

# Marpで研究発表スライドを作る

### 〜Beamerを卒業しよう〜

<br>

**著者 太郎**
ほげほげ研究室 M2
YYYY/MM/DD

---

# 目次

1. はじめに
1. コードブロック
1. 数式
1. 図・デザイン要素

---

# はじめに

## Marp とは

- **Markdown** でスライドを作成するためのソフトウェア
  - 基本的な Markdown のシンタックスがサポートされている
- `---` という区切り線を入れるだけで次のページに移動できる

## このテーマの使い方

- `#`（h1）がスライド上部のヘッダーバーとして自動表示される
- `##`（h2）がスライド本文の見出しになる

> 脚注は blockquote (`>`) で書くとスライド下部に固定表示されます。

---

# コードブロック

## Python の例

```python
import torch
print(torch.cuda.is_available())
```

```python
from transformers import AutoModelForMaskedLM, AutoTokenizer

model = AutoModelForMaskedLM.from_pretrained("cl-tohoku/bert-base-japanese-whole-word-masking")
tokenizer = AutoTokenizer.from_pretrained("cl-tohoku/bert-base-japanese-whole-word-masking")

inputs = tokenizer.encode_plus("私はとても[MASK]です。", return_tensors='pt')
outputs = model(**inputs)
tokenizer.convert_ids_to_tokens(outputs.logits[0][1:-1].argmax(axis=-1))
```

横幅は自動調整される（[Auto-scaling](https://github.com/marp-team/marp-core#auto-scaling-features) 参照）。

---

# 数式

## KaTeX による数式表示

ブロック数式：

$$ I_{xx}=\int\int_Ry^2f(x,y)\cdot{}dydx $$

$$
f(x) = \int_{-\infty}^\infty \hat f(\xi)\,e^{2 \pi i \xi x}\,d\xi
$$

インライン数式 $\LaTeX$ も使える。

---

# 図・デザイン要素

## マーカーと吹き出し

<span class="marker">重要なキーワード</span> はマーカーで強調できる。

<div class="bubble">
スライドの結論や重要なメッセージをここに書く
</div>

## 2カラムレイアウト

<div class="two-columns">
  <div class="column">

**左カラム**
- 比較項目 A
- 比較項目 B

  </div>
  <div class="column">

**右カラム**
- 比較項目 X
- 比較項目 Y

  </div>
</div>

---

<!-- _class: lead -->

# ご清聴ありがとうございました

## Questions?
