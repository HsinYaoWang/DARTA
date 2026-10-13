# Know what you are licensing before you commit

[DARTA](README.md) · [Workflow demo](docs/walkthrough.md) · [繁體中文](#繁體中文)

## An MRSA research example

A team wants to develop a model using MALDI-TOF measurements of *S. aureus* and reference laboratory labels for methicillin resistance. A seller's record count is a starting point. The buyer also needs to understand **which records are usable, whether they fit the research question, and what additional data would help.**

DARTA's planned review service brings those questions into the purchasing conversation. Sellers can explain their data's strengths and limitations; buyers can agree a suitable scope of authorized use before committing a larger budget.

> **Synthetic assessment demo:** The quality-review funnel and quantity-planning calculations are hypothetical. Section 4 adds measured results from actual training on newly generated synthetic data. Neither uses the historical MRSA dataset or represents an available listing, clinical study or deployed production assessment service.

## 1. Review quality and fit

| What the buyer needs to know | What the assessment should explain |
|---|---|
| **Can we use it for this project?** | Source, authorization, permitted purposes and any restrictions. |
| **Can we interpret the measurements and labels?** | Measurement method, required fields, reference-label provenance, missingness and consistency. |
| **How much usable data is there?** | Counts before and after review, repeated measurements and exclusions, with clear denominators. |
| **Does it represent our intended setting?** | Relevant population, source, time-period and resistance-class coverage; important gaps. |
| **What has actually been demonstrated?** | Separate measured quality, task fit and any model experiment; identify what remains unassessed. |

The report belongs to a specific dataset version and identifies its reviewer, date, scope and limitations. Buyer-facing summaries follow the agreed disclosure rules; raw patient records are not part of this public example or a buyer download.

## 2. Turn a record count into a usable cohort

**Hypothetical quality review — sequential, non-overlapping exclusions:**

| Review step | Removed at this step | Records remaining |
|---|---:|---:|
| Start with an authorized, in-scope candidate pool | — | 10,000 |
| Required measurement or reference label is missing | 1,000 | 9,000 |
| Repeated records excluded under the agreed analysis rule | 500 | 8,500 |
| Remaining records do not meet the agreed quality criteria | 500 | **8,000** |

The example retains **80%** of the candidate records. Assume the retained cohort contains **1,600 MRSA-labeled records (20%)** and **6,400 non-MRSA-labeled records (80%)**. These are fictional class counts, not a prevalence estimate. Repeated measurements are not automatically independent samples; the report must also describe participant/specimen grouping.

## 3. Estimate a starting scope

Suppose the buyer chooses **400 usable MRSA-labeled records** as an initial development-planning target. This is a scenario assumption, not a recommended minimum.

| Planning question | Illustrative calculation |
|---|---:|
| At the same 20% class mix, how many usable records would that imply? | 400 ÷ 20% = **2,000** |
| At the same 80% retention rate, how many candidates would need screening? | 2,000 ÷ 80% = **2,500** |

This estimate assumes the same class mix and retention rate in the selected pool. Actual reviewed counts replace it before the scope is agreed. **2,500 is a screening estimate, not an automatic billable quantity.** Price, permitted cohort, work and billing basis are agreed separately. Independent validation/test cohorts need their own allocation.

## 4. Decide whether more data would help

We actually trained a generic demonstration model at **100, 250, 500, 1,000, 2,000 and 4,000 training records**, with 10 predetermined subset orderings at each size. Every run was evaluated on the same separate 1,000-record development-validation cohort. Another 1,000 generated records were reserved for final testing and were not evaluated.

![Measured synthetic learning curves: mean AUROC rises from 0.842 to 0.918 and mean Brier error falls from 0.120 to 0.079 as training grows from 100 to 4,000 records. Bands show observed ranges, not confidence intervals.](assets/mrsa-learning-curve-en.png)

*Actual measurements on generated data. Lines are means; bands are observed minimum–maximum results across 10 training-subset orderings. They do not measure uncertainty from new validation cohorts or clinical populations. Inputs are generic random features, not patient records or actual MALDI-TOF spectra.*

| Training records | Mean AUROC ↑ | AUROC range across runs | Mean Brier error ↓ |
|---:|---:|---:|---:|
| 100 | 0.8416 | 0.7850–0.8742 | 0.1203 |
| 250 | 0.8797 | 0.8538–0.8977 | 0.1029 |
| 500 | 0.8973 | 0.8826–0.9118 | 0.0914 |
| 1,000 | 0.9110 | 0.9029–0.9185 | 0.0827 |
| 2,000 | 0.9161 | 0.9131–0.9193 | 0.0798 |
| 4,000 | 0.9179 | 0.9166–0.9190 | 0.0787 |

**What changes for the buyer's decision?** In this simulation, increasing from 1,000 to 2,000 records adds about **0.0051 mean AUROC**. Increasing from 2,000 to 4,000 adds about **0.0019**, with mean Brier error improving by about **0.0011**; some paired runs worsen. The smaller average gain is a reason to compare the next batch's cost, coverage and uncertainty. It does not establish that 2,000 records are sufficient or optimal.

The earlier 10,000 → 8,000 quality funnel was not measured in this experiment. Its screening yield cannot be used to turn this curve into a real order quantity. A real project needs verified usable counts, permitted uses, agreed costs and evaluation of its own data, source/subgroup coverage and goals. No count here is a minimum purchase recommendation or evidence of clinical validity.

**[See the experiment scope, additional metrics and aggregate results →](docs/mrsa-learning-curve.md)**

**The buyer's deliverable:** a versioned quality summary, usable-cohort counts, task-fit limitations and a scoped next step. A model-utility study, when commissioned, adds evidence for expanding or stopping. The buyer and seller still agree the price.

**[Discuss your data or research project →](docs/collaborate.md)**

---

## 繁體中文

### 先看懂資料，再決定授權範圍

假設研究團隊希望利用金黃色葡萄球菌的 MALDI-TOF 量測與參考實驗室抗藥標籤，開發 MRSA 相關研究模型。買方需要知道：**哪些資料可用、是否適合這個問題，以及還需要補多少、哪一類資料。**

DARTA 規劃在買方決定採購範圍前，提供賣方資料的品質與適用性評估。讓賣方說明資料優勢與限制，也讓買方有依據地安排預算與資料使用授權。

> **合成評估展示：** 品質篩選流程與數量估算是情境假設；後段學習曲線則是全新合成資料實際訓練的量測結果。兩者都沒有使用歷史 MRSA 資料集，也不代表可購商品、臨床研究或已部署的正式評估服務。

### 買方會看見什麼

| 評估面向 | 報告回答的問題 |
|---|---|
| **來源與權利** | 誰提供、允許哪些用途、有什麼限制？ |
| **品質與標籤** | 量測與參考標籤如何取得？必要欄位是否完整、一致？ |
| **可用數量** | 審核前後有多少？重複量測與各項排除如何計算？ |
| **研究適用性** | 族群、來源、時間與抗藥類別是否符合需求？缺口在哪裡？ |
| **證據範圍** | 哪些品質已量測、哪些用途已評估、哪些模型效益尚未驗證？ |

報告標示資料版本、審核者、日期、範圍與限制。買方取得經核准揭露的摘要；公開案例與買方下載均不提供原始患者紀錄。

### 從總筆數，算出本案可用範圍

以下依序排除，每筆只在首次不符合的步驟扣除：

| 假設審核步驟 | 本步排除 | 剩餘筆數 |
|---|---:|---:|
| 已授權且符合範圍的候選資料 | — | 10,000 |
| 缺必要量測或參考標籤 | 1,000 | 9,000 |
| 依約定分析規則排除重複紀錄 | 500 | 8,500 |
| 其餘未通過約定品質條件的紀錄 | 500 | **8,000** |

範例保留率為 **80%**。再假設其中 MRSA 標籤有 **1,600 筆（20%）**，非 MRSA 標籤有 **6,400 筆（80%）**。這是虛構類別組成，不是盛行率估計；重複量測也不等於獨立樣本，報告須另說明患者／檢體的群組關係。

若買方先以 **400 筆可用 MRSA 標籤資料**作為開發規劃目標：

- 相同類別組成下，需要約 **400 ÷ 20%＝2,000 筆可用資料**。
- 相同保留率下，需先篩選約 **2,000 ÷ 80%＝2,500 筆候選資料**。

400 只是這個情境的規劃假設，不是建模最低樣本數。實際審核數量會取代估算，再約定範圍。**2,500 是篩選量估計，不會自動成為計費筆數。** 價格、授權範圍、工作與計費基礎另行約定；獨立驗證與測試資料也須另外配置。

### 要不要再買，接著看什麼

我們已實際比較 **100、250、500、1,000、2,000、4,000 筆訓練資料**，每種數量依事先固定的 10 組子集順序訓練。每次都使用另外固定的 **1,000 筆開發驗證資料**評估；另有 1,000 筆合成資料保留作最終測試，本次沒有評估它。

![合成資料學習曲線：訓練量從 100 增至 4,000 筆，平均 AUROC 從 0.842 升至 0.918，平均 Brier 誤差從 0.120 降至 0.079。色帶為各次結果範圍，並非信賴區間。](assets/mrsa-learning-curve-zh-TW.png)

*這是生成資料上的實測結果。實線為平均，色帶為 10 次訓練子集順序產生的最小至最大值，不涵蓋更換驗證組或真實臨床族群的不確定性。輸入是一般隨機特徵，不是患者紀錄或真實 MALDI-TOF 光譜。*

| 訓練筆數 | 平均 AUROC ↑ | 各次 AUROC 範圍 | 平均 Brier 誤差 ↓ |
|---:|---:|---:|---:|
| 100 | 0.8416 | 0.7850–0.8742 | 0.1203 |
| 250 | 0.8797 | 0.8538–0.8977 | 0.1029 |
| 500 | 0.8973 | 0.8826–0.9118 | 0.0914 |
| 1,000 | 0.9110 | 0.9029–0.9185 | 0.0827 |
| 2,000 | 0.9161 | 0.9131–0.9193 | 0.0798 |
| 4,000 | 0.9179 | 0.9166–0.9190 | 0.0787 |

**這如何幫買方決策？** 這個模擬中，從 1,000 增至 2,000 筆，平均 AUROC 增加約 **0.0051**；從 2,000 增至 4,000 筆，平均再增加約 **0.0019**，平均 Brier 誤差改善約 **0.0011**，部分配對抽樣結果反而略降。新增資料的平均增益變小時，就應一起比較下一批的成本、涵蓋範圍與不確定性；不能據此宣稱 2,000 筆已足夠或最划算。

前面的 10,000 → 8,000 品質篩選並非本次量測，不能把假設保留率套在這條曲線上換算真實訂單。正式專案須依賣方確認的可用數量、授權、報價，以及本案資料、來源／子群與研究目標的評估結果來決定。這裡沒有推薦最低採購筆數，也不代表臨床有效性。

**[看實驗範圍、其他指標與彙總結果 →](docs/mrsa-learning-curve.md#繁體中文)**

**買方得到的成果：** 有版本的品質摘要、可用資料數、適用性限制與下一步範圍；若另行委託模型效益研究，再以實測證據判斷擴大或停止。成交價仍由買賣雙方約定。

**[討論你的資料或研究需求 →](docs/collaborate.md#繁體中文)**
