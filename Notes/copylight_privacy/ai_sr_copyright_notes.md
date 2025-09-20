# Cao2025, Lai2024, Trad2025 におけるAI利用と著作権・ライセンスの記載

本リポジトリ内のPDF（Cao2025, Lai2024, Trad2025）をテキスト化した上で、Systematic Review作成におけるAI活用の有無と、著作権・ライセンス・権利関係の明示について確認した要約です。

## 結論サマリ
- Cao2025 は、全文取得の実務的制約として「購読料の壁（paywalls）」や「著作権上の懸念」を明確に言及。
- Lai2024 は、論文自体が CC BY（オープンアクセス）で公開。AI 活用に伴う著作権・権利処理の踏み込んだ議論はなし。
- Trad2025 は、論文自体が CC BY-NC-ND 4.0（非営利・改変不可）で公開。AI 活用に伴う著作権・権利処理の踏み込んだ議論はなし。

---

## Cao2025
- AI 利用: LLM（GPT-4 系ほか複数モデル）を用いて SR の抄録・全文スクリーニングを実施。
- 著作権・ライセンス関連の言及:
  - Full-text 取得に関する実務的制約として「購読料の壁」「著作権上の懸念」を明記。
    - 該当箇所（`Cao2025.txt` 1760–1763 行）: “Journal paywalls, copyright concerns, and other associated costs preclude complete full-text retrieval.”
  - PMC にある「自由に利用可能な」全文に限定して解析を行った旨の記載（本文および補足資料）。
  - コスト見積り文脈で「software licenses」への言及はあるが、AI 生成物の権利や二次利用ポリシーの詳細な方針は特に見当たらず。

## Lai2024
- AI 利用: ChatGPT（LLM1）と Claude（LLM2）を用い、RCT の Risk of Bias 評価を検証。
- 著作権・ライセンス関連の言及:
  - 論文は CC BY のオープンアクセス。
    - 該当箇所（`Lai2024.txt` 76 行、990 行）: “Open Access… distributed under the terms of the CC-BY License.”
  - AI 活用に関する著作権・利用規約（PDF 取り扱い、AI 生成物の権利帰属、各サービスの ToS 準拠等）についての詳細な記載は確認できず。

## Trad2025
- AI 利用: GPT-4 と RAG によるタイトル/抄録・全文スクリーニングの自動化を検証。
- 著作権・ライセンス関連の言及:
  - 論文は CC BY-NC-ND 4.0（非営利・改変不可）。
    - 該当箇所（`Trad2025.txt` 49–56 行）: “Open Access… Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License… you do not have permission … to share adapted material…”
  - AI 活用に伴う著作権・権利処理（全文 PDF の取得やベクトル化の可否、プラットフォームの ToS 順守等）の明示的な方針は見当たらず。

---

## 参考（リポジトリ内ファイル）
- 原文テキスト化ファイル: `Cao2025.txt`, `Lai2024.txt`, `Trad2025.txt`
- 補足資料テキスト化ファイル: `Cao2025_Sup.txt`, `Lai2024_Sup1.txt`, `Lai2024_Sup2.txt`

必要に応じて、該当箇所の原文抜粋や位置（行番号）の追加提示も可能です。
