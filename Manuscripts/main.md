# AI支援によるSystematic Reviewの効率化と信頼性向上に関する研究

## Abstract

AI技術の急速な発展により、学術研究における文献レビューの自動化・効率化への期待が高まっている。本研究では、AI Agent（特にLarge Language Models: LLM）を活用したSystematic Reviewプロセスの最適化について検討し、複数モデルによるデータ抽出アプローチの有効性を実証的に分析する。従来の手動によるSystematic Reviewと比較して、AI支援によるアプローチは時間効率性を大幅に改善しつつ、複数モデル・複数回実行戦略により信頼性の向上も実現可能であることを示す。

**Keywords:** Systematic Review, Large Language Models, AI Agent, Multi-Model Approach, Literature Review Automation

## 1. Introduction

### 1.1 背景

Systematic Reviewは、特定の研究課題に対して既存の研究エビデンスを体系的かつ網羅的に収集・評価・統合する研究手法であり、Evidence-Based Medicine（EBM）の中核をなしている。PRISMAガイドライン[1]に代表される厳格な手順に従い、文献検索、スクリーニング、データ抽出、質的評価、結果統合の各段階を透明性と再現性を保ちながら実施することが求められる。

しかし、近年の学術論文数の爆発的増加により、従来の手動によるSystematic Reviewには以下の課題が顕在化している：

1. **膨大な時間コスト**: 文献検索から最終報告書作成まで通常6ヶ月から2年を要する
2. **人的リソースの制約**: 複数の研究者による独立したスクリーニングとデータ抽出が必要
3. **主観性とバイアスのリスク**: 人間の判断に依存する部分でのinter-rater reliability の課題
4. **再現性の困難**: 検索戦略や選択基準の解釈に研究者間の差異が生じる可能性

### 1.2 AI技術の応用可能性

近年のAI技術、特にLarge Language Models（LLMs）の発展は、これらの課題に対する解決策を提供する可能性を秘めている。ChatGPT、Claude、Geminiなどの高性能LLMsは、自然言語処理、文書理解、論理的推論において人間に近い性能を示しており、Systematic Reviewの各段階での活用が期待されている。

### 1.3 研究目的

本研究の目的は以下の通りである：

1. AI Agent活用によるSystematic Review効率化の実証的評価
2. 複数モデル・複数回実行によるデータ抽出精度向上の検証
3. AI支援Systematic Reviewにおけるベストプラクティスの提案
4. 従来手法との比較による有効性・信頼性の定量的評価

## 2. Literature Review

### 2.1 Systematic Reviewの標準的プロセス

Cochrane Handbookに基づく標準的なSystematic Reviewプロセスは以下の段階から構成される[2]：

1. **研究課題の設定（PICO/PECO Framework）**
   - P (Population): 対象集団
   - I (Intervention): 介入
   - C (Comparison): 比較対照
   - O (Outcome): 評価項目

2. **プロトコル作成と事前登録**（PROSPERO等）

3. **文献検索戦略の策定**
   - 複数データベースの利用（PubMed, Scopus, Web of Science等）
   - 検索式の最適化（MeSH terms, keywords）

4. **文献スクリーニング**
   - Title/Abstract screening
   - Full-text review

5. **データ抽出と質的評価**
   - 標準化されたデータ抽出フォーム
   - Risk of Bias評価（RoB 2, Newcastle-Ottawa Scale等）

6. **結果統合と解釈**
   - Meta-analysis（可能な場合）
   - Narrative synthesis

### 2.2 AI支援文献レビューの先行研究

#### 2.2.1 単一モデルによるアプローチ

ResearchGateの2025年研究[3]では、AI支援データ抽出の有効性が実証されている：
- 精度: 91.0%（Recall: 89.4%, Precision: 98.9%）
- 人間のみの手法との比較: 誤抽出率 AI支援9.0% vs 人間のみ11.0%
- 時間効率: 1研究あたり中央値41分の短縮

#### 2.2.2 協調型LLMアプローチ

2024年の協調型LLM研究[4]では、複数モデルの相互作用による精度向上が報告されている：
- 一致応答での精度: 0.94
- 不一致応答の改善: 相互批評により0.41-0.50から0.76へ
- コンセンサス形成: 不一致応答の51%が相互批評後に一致

### 2.3 LLMの非決定性とBatch Invariance

Xenospectrum研究所の最新研究[5]により、LLMの非決定性は従来考えられていたGPU並列処理の問題ではなく、「batch invariance」の欠如に起因することが明らかになった。この発見は、複数回実行による信頼性向上戦略の理論的根拠を提供する。

## 3. Methodology

### 3.1 研究デザイン

本研究では、AI支援Systematic Reviewの効果を検証するため、以下の比較研究デザインを採用する：

1. **従来手法群**: 標準的な手動Systematic Review
2. **単一AI群**: 単一LLMによる支援
3. **複数AI群**: 複数LLM（Claude, GPT-4, Gemini）による支援
4. **ハイブリッド群**: AI支援＋人間による最終検証

### 3.2 対象文献と選択基準

**研究課題**: 「医療分野におけるAI診断支援システムの有効性に関するSystematic Review」

**選択基準**:
- 2020年以降に発表された査読済み論文
- 英語で記述された原著論文
- 医療AI診断に関する定量的評価を含む研究

### 3.3 評価指標

1. **効率性指標**
   - 処理時間（文献スクリーニング、データ抽出各段階）
   - 人的コスト（時間×人数）

2. **精度指標**
   - Sensitivity（感度）
   - Specificity（特異度）
   - Inter-rater reliability（κ係数）

3. **品質指標**
   - データ抽出の完全性
   - バイアス評価の一貫性

### 3.4 複数モデル戦略

#### 3.4.1 モデル選択
- **Claude 3.5 Sonnet**: 長文理解と論理的推論に優れる
- **GPT-4**: 医療知識と一般的推論のバランス
- **Gemini Pro**: 多言語対応と画像認識機能

#### 3.4.2 実行戦略
1. **並列実行**: 各モデルが独立してタスクを実行
2. **結果統合**: 多数決または重み付き投票による決定
3. **不一致解決**: 人間による最終判断または追加モデルでの検証

## 4. Expected Results and Discussion

### 4.1 予想される結果

先行研究に基づき、以下の結果が予想される：

1. **時間効率の大幅改善**: 従来手法比50-70%の時間短縮
2. **精度の維持・向上**: 複数モデルアプローチにより90%以上の精度達成
3. **一貫性の向上**: Inter-rater reliabilityの改善（κ > 0.8）

### 4.2 限界と課題

1. **コスト**: 複数モデルの利用による計算コスト増加
2. **専門性**: 高度に専門的な医療知識の理解限界
3. **倫理的配慮**: AI判断の透明性と説明可能性

### 4.3 今後の発展方向

1. **特化型モデルの開発**: 医療分野特化LLMの活用
2. **リアルタイム更新**: Living Systematic Reviewへの対応
3. **標準化**: AI支援レビューのガイドライン策定

## 5. Conclusion

本研究は、AI Agent、特に複数LLMを活用したSystematic Reviewの効率化と信頼性向上について実証的に検討する。従来の手動プロセスが直面する時間・人的コスト、主観性、再現性の課題に対し、AI技術を適切に組み合わせることで、より効率的かつ信頼性の高いSystematic Reviewプロセスの実現可能性を探る。

複数モデル・複数回実行戦略は、LLMの非決定性という課題を逆手に取り、アンサンブル効果による精度向上を実現する革新的アプローチである。本研究の成果は、Evidence-Based Medicineの発展とともに、学術研究全般における文献レビューの質的向上に貢献することが期待される。

## References

[1] Page, M. J., et al. (2021). The PRISMA 2020 statement: an updated guideline for reporting systematic reviews. BMJ, 372, n71.

[2] Higgins, J. P., et al. (2019). Cochrane handbook for systematic reviews of interventions. John Wiley & Sons.

[3] Gartlehner, et al. (2025). AI-Assisted Data Extraction with a Large Language Model: A Study Within Reviews. ResearchGate.

[4] Khan, et al. (2024). Collaborative Large Language Models for Automated Data Extraction in Living Systematic Reviews. ResearchGate.

[5] Xenospectrum Research Lab. (2024). LLM Non-determinism and Batch Invariance. Retrieved from https://xenospectrum.com/thinking-machines-lab-llm-nondeterminism-batch-invariance/

## Appendices

### Appendix A: PRISMA Flow Diagram Template
[フローダイアグラムのテンプレート]

### Appendix B: Data Extraction Forms
[データ抽出フォームの詳細]

### Appendix C: AI Prompt Templates
[各LLMで使用するプロンプトテンプレート]

---

*Manuscript prepared using AI-assisted writing tools with human oversight and validation.*
