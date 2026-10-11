# AIパートナーの判断層としてDecision Modelは使えるか

判断専用AI **Jev 1.13.0**（TypeSafe AI）を、AIパートナー／キャラクターAIで必要になる4種類の判断タスクで評価し、汎用LLM 4モデル（GPT-6 Luna、GPT-6 Astra、Gemini 3.1 Pro Preview、Gemini 3.8 Flash）と比較した技術レポートです。

- **本文（技術版）**：[index.html](index.html)（GitHub Pages: https://whitelabel1940.github.io/jev-ai-partner-decision-eval/ ）
- **一般向けの解説記事（note）**：[AIパートナーの「判断」にJevは使えるか？ ―― GPT-6・Geminiと256問で比べた結果](https://note.com/whitelabel1940/n/ndf19a5059f65)
- **続編（技術版）**：[Decision Modelは判断を控えられるか：7つのDecision Modelによるholdout-exp-2横断評価](https://whitelabel1940.github.io/decision-model-comparison-v1/)

## 概要

- Goldを生成側から隔離した256問（provider cases）のholdoutを、一発勝負で実行した。
- Jevの正答率は162/256（63.3%）で、汎用4モデル（68.8〜74.2%）をいずれも下回った。汎用4モデル平均との差は−0.085。
- Jevの頑健な弱点は、根拠が不足しているのに判断を確定すること、今の発言と食い違う記憶の取り違え、表現planの過剰な受容の3つ。
- Jevの自信度（margin）を使った二段構え（cascade）は、高価格の汎用モデルを控えにした場合に31〜39%の費用削減を示した。ただし、最も正確で安価だったGPT-6 Lunaを控えにすると、Luna単体より約1.7%高くなった。
- 現時点の実務的な結論：**安価で強い汎用LLMがあるなら、それを直接判断役に使う方が合理的である。**

詳細、限界、感度分析は本文を参照してください。

## このリポジトリに含まれないもの

- holdoutの問題・正解（Gold）・実行ログは公開していません。将来、別の判断専用モデルを同じ条件で比較するときに再利用するためです。
- 本文中の例は、すべて説明用に作った架空例です。

## 改訂履歴

改訂の履歴はこのリポジトリのコミット履歴で確認できます。誤りの指摘はIssueで受け付けています。

## ライセンス

本文と図は [CC BY 4.0](LICENSE) で公開しています。出典（著者名とこのリポジトリのURL）を明記すれば、改変・再配布できます。

## 引用

```
whitelabel1940. AIパートナーの判断層としてDecision Modelは使えるか：Jev 1.13.0と4つの汎用モデルによるholdout評価. 2026.
https://github.com/whitelabel1940/jev-ai-partner-decision-eval
```
