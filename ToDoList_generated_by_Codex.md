**ToDoList.md**

- 本リポジトリ内の主要ファイルを確認し、現状から完遂までの作業を整理しました。
- 参照元: `Manuscripts/main.md`, `ToDo.txt`, `Notes/*`, `References/*`, `AGENTS.md`

**Manuscript**

- タイトル確定と一貫性
  - 現在: `AI支援によるSystematic Reviewの効率化と信頼性向上に関する研究`
  - 候補: “Write Reviews with AI Agents” との整合を決める（和名/英名併記方針）。
- イントロの定量的根拠を補強
  - 「近年の学術論文数の爆発的増加」の出典を明示（Scopus/WoS/AI Index等）。
  - 「6ヶ月〜2年」の所要期間の出典を明示（Cochrane/PRISMA関連の方法論論文等）。
- 用語と定義の統一
  - Review / Systematic Review / Meta-analysis の差異を明文化（`Notes/Systematic_Review_Methodology.md` 反映）。
  - PICO, PROSPERO, RoB, Narrative synthesis の定義と採用方針を記載。
- 方法論の具体化
  - 対象テーマの最終確認（現行: 「医療分野AI診断支援の有効性」）。範囲・期間・母集団・アウトカム確定。
  - 検索式（データベース別、MeSH/keywords）を本文/付録に掲載。
  - スクリーニング手順（Title/Abstract/Full-text、ダブルスクリーン、衝突解消）を明文化。
  - データ抽出項目表を付録化（研究デザイン、対象、介入、比較、アウトカム、指標など）。
  - バイアス評価ツール（RoB2等）の採用根拠と判定手順を明記。
- AI活用パートの設計
  - 単一/複数モデル、複数回実行、合意形成（多数決/加重投票/ルールベース）を仕様化。
  - インターネットアクセス制御と参照制限（`AGENTS.md`に方針を追記）を本文に透明化。
  - ローカルLLM活用方針（機密/コスト/再現性の観点）を記述。
- 期待結果と限界
  - `Notes/Multi_Model_Data_Extraction_Analysis.md` のエビデンスを本文に統合。
  - コスト・倫理・説明可能性・再現性の制約を整理。
- 参考文献
  - `References/pdf/*`, `References/md/*` の引用整備（BibTeX化/番号整合、URL/DOI付与）。
  - 本文の [1]–[5] が実ファイルと一致するか最終チェック。

**Protocol & Assets**

- 付録テンプレ整備（`Commons/` 推奨）
  - PRISMAフローダイアグラムのテンプレ（.drawio/.svg/.pptx）。
  - データ抽出フォーム（CSV/TSV/JSON Schema/Markdown表）。
  - AIプロンプトテンプレ（モデル別、用途別: スクリーニング/抽出/要約）。
- 研究事前登録（必要なら）
  - PROSPERO等への登録可否、多言語対応（和/英）判断と手順整備。
- ログと監査性
  - スクリーニング・抽出ログ（日時、操作者、モデル、温度、リトライ回数）仕様。

**Search & Screening**

- 検索戦略の確定
  - 対象DB（PubMed/Scopus/WoS/Cochrane 等）と期間・言語・対象タイプ。
  - 再現可能な検索式の保存（`Commons/search_queries/`）。
- スクリーニング実施計画
  - Title/Abstract → Full-text の基準、二名独立レビュー手順、Kappa算出方法。
  - ツール選定（Rayyan/Excel/独自CSV運用）とファイル設計。
- スケール・見積り
  - 想定ヒット件数、工数、AI/人手の分担比率の概算。

**AI Tooling**

- CLI/Agent環境の標準化（`Notes/data_extraction_guidance/guidance_for_ai_ver3.md` 反映）
  - 採用ツール（Claude Code / Gemini CLI / Cursor / OpenHands 等）の最終決定。
  - モデル一覧（Claude, GPT-4/4o, Gemini 2.5 Pro 等）と用途割当。
  - セッション設定（温度、max tokens、再試行回数、投票ルール）を定義化。
- 参照制御・RAG
  - ローカル資料限定モード/ネット許可切替の運用ルールを `AGENTS.md` に明記。
  - RAG/GraphRAG 採否と実験計画（小規模PoC→本番の段階実装）。
- マルチラン・コンセンサス
  - N回実行のN、投票スキーム（多数決/信頼度重み/モデル優先度）を固定。
  - 不一致時の追加手順（人手確認/追加モデル）を定義。

**Data Preparation**

- 入力データ最適化
  - PDF→Markdown変換パイプライン整備（見出し/表/図の扱い基準、ノイズ除去）。
  - 図表は原則PNG（可逆、精細）運用。写真類のみ高画質JPEG例外を許容（`Notes/PNG_vs_JPEG_for_AI.md`）。
  - トークン上限対策（セクション分割、チャンク化ポリシー）。
- 画像/表取り扱い
  - 画像OCR/テーブル抽出の手順と再確認フロー。
  - 画像認識モデル選択（`Notes/AI_Models_Image_Recognition_Comparison.md` を踏まえClaude系優先か検証）。

**Experiments & Evaluation**

- 実験設計
  - 比較群: 手動/単一AI/複数AI/ハイブリッドの明確化と評価指標（時間、精度、IRR）。
  - 再現パラメタ（乱数、温度、プロンプト、チャンク設定、モデルバージョン）。
- 指標算出
  - 感度・特異度、κ係数、処理時間、人件コストの算出方法と記録形式。
- 解析
  - メタ解析可否判断、Narrative synthesisの構成案。
  - 図表（フォレスト/棒/箱ひげ）仕様と作図ツール選定。

**Figures, Tables, Commons**

- `Commons/` の作成と運用
  - 図表データ（CSV/JSON）、図版（SVG/PNG）、テンプレ（PRISMA/フォーム/プロンプト）を集約。
  - ファイル命名規則とバージョニング（`vYYYYMMDD`準拠など）。

**Ethics, Legal, Copyright**

- 著作権・ライセンス整理（`Notes/copylight_privacy/*` 反映）
  - Open Access/CCライセンス確認、非OAの扱い、引用/転載の範囲。
  - 解析対象PDFの権利面チェックとログ化。
- 外部書籍・資料のデジタイズ
  - 「LLMのプロンプトエンジニアリング」書籍PDF化の可否確認（私的複製/引用範囲/研究利用）。
  - 社外非公開データの取り扱い基準（ローカル限定/クラウド禁止等）。

**References Management**

- 参考文献の一元管理
  - BibTeX化（`Manuscripts/references.bib`）または `Commons/bibliography/`。
  - `References/md/*` と本文引用の整合。DOI/URL/アクセス日付。
- 付随資料
  - 研究ごとのアノテーション、重要図表のサマリ作成。

**Repo & Process**

- `AGENTS.md` 更新
  - インターネットアクセス切替手順、参照範囲制御、出力フォーマット、再現ルール追記。
- ToDo管理
  - 現行 `ToDo.txt` の項目を本 `ToDoList.md` に移行・統合。以後はこちらで管理。
- 構成・命名・無視設定
  - `Commons/` 追加、`.gitignore` 整備（サイズ大/秘匿ファイル除外）。
  - 日本語ファイル名方針（可/不可）を決定し、クロスプラットフォーム配慮。
- 進捗運用
  - マイルストーン/デッドライン設定、週次進捗（Draft→Revise→Finalize）。

**Milestones**

- M1: プロトコル草案・付録テンプレ（PRISMA/抽出フォーム/プロンプト）準備
- M2: 検索式確定・スクリーニング小規模パイロット
- M3: AI抽出パイロット（単一/複数モデル、N回実行、合意形成手順検証）
- M4: 本番スクリーニング/抽出・評価指標集計
- M5: 原稿ドラフト完成・図表整備・参考文献整合
- M6: 内部査読→投稿先体裁調整→提出

**Open Questions（要ご回答）**

- 研究対象の確定
  - 現行の対象（医療AI診断支援）で確定か、方法論中心のメソッド論文として一般化するか。
- 実施範囲
  - 実データで小〜中規模の実証（検索/スクリーニング/抽出）まで行うか、それとも概念実証と設計提案中心か。
- 投稿先
  - 目標学会/ジャーナル（スタイル/文字数/引用形式/査読言語）を教えてください。
- ツールと制約
  - 使用可能なLLM/CLIツール、インターネット接続可否、クラウド利用ポリシー、予算上限。
- 法務・権利
  - 書籍PDF化の扱い可否、非OA論文の取り扱いルールの希望。
- 言語方針
  - 原稿は日本語/英語のどちらを最終形とするか（和英併記の範囲）。

