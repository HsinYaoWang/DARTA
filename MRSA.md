# Know what you are licensing before you commit

[DARTA](README.md) · [Workflow demo](docs/walkthrough.md) · [繁體中文](#繁體中文)

## An MRSA research example

A team wants to develop a model using MALDI-TOF measurements of *S. aureus* and reference laboratory labels for methicillin resistance. A seller's record count is a starting point. The buyer also needs to understand **which records are usable, whether they fit the research question, and what additional data would help.**

DARTA's planned review service brings those questions into the purchasing conversation. Sellers can explain their data's strengths and limitations; buyers can agree a suitable scope of authorized use before committing a larger budget.

> **Illustrative assessment demo:** All counts and proportions below are invented for this example. They are not results from the historical MRSA dataset, an available data listing, or a completed clinical study. This page demonstrates the intended report and decision process; a production MRSA assessment service is not deployed.

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

For an agreed model-development study, compare increasing training subsets while keeping the evaluation protocol fixed and related records in the same split. Use a learning curve, uncertainty, error/calibration measures and source/subgroup results to assess the next purchase. Reserve the final test set from repeated purchasing decisions.

- **Performance still improves:** assess a larger authorized training cohort within budget.
- **A source or subgroup remains weak:** seek data that address that gap.
- **Gains flatten or uncertainty remains large:** examine labels, coverage and the model before expanding the order.

This example reports no measured learning curve or model performance. Data quantity and quality alone do not establish clinical validity or guarantee a useful model.

**The buyer's deliverable:** a versioned quality summary, usable-cohort counts, task-fit limitations and a scoped next step. A model-utility study, when commissioned, adds evidence for expanding or stopping. The buyer and seller still agree the price.

**[Discuss your data or research project →](docs/collaborate.md)**

---

## 繁體中文

### 先看懂資料，再決定授權範圍

假設研究團隊希望利用金黃色葡萄球菌的 MALDI-TOF 量測與參考實驗室抗藥標籤，開發 MRSA 相關研究模型。買方需要知道：**哪些資料可用、是否適合這個問題，以及還需要補多少、哪一類資料。**

DARTA 規劃在買方決定採購範圍前，提供賣方資料的品質與適用性評估。讓賣方說明資料優勢與限制，也讓買方有依據地安排預算與資料使用授權。

> **評估報告示範：** 以下數字與比例全部為虛構，沒有沿用歷史 MRSA 資料集的分析結果，也不代表可購買的商品或完成的臨床研究。目前呈現預定的報告與決策流程，正式 MRSA 評估服務尚未部署。

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

若委託模型效益評估，可在固定評估設計下比較不同訓練量，讓同一患者／檢體的相關紀錄留在同一切分，以學習曲線、不確定性、錯誤／校準與來源／子群表現，決定下一步。最終測試集保留到最後，避免反覆用它挑選採購方案。

仍持續改善時，評估擴大訓練授權；特定來源或子群不足時，補足缺口；增益趨緩或不確定性仍大時，先檢視標籤、涵蓋範圍與模型。本頁沒有宣稱已量測的學習曲線或模型效能，資料量與品質本身也不代表臨床有效性。

**買方得到的成果：** 有版本的品質摘要、可用資料數、適用性限制與下一步範圍；若另行委託模型效益研究，再以實測證據判斷擴大或停止。成交價仍由買賣雙方約定。

**[討論你的資料或研究需求 →](docs/collaborate.md#繁體中文)**
