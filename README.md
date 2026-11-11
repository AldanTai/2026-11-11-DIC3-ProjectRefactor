# Food Guardian 上傳附件索引（2026-11-11）

> **專題：** Food Guardian — 智慧食材管理及家庭食物浪費減量 AI Agent  
> **Repository：** [AldanTai/2026-11-11-DIC3-ProjectRefactor](https://github.com/AldanTai/2026-11-11-DIC3-ProjectRefactor)  
> **資料目錄：** [`/myplan`](./myplan)  
> **用途：** 彙整專題規劃、課程要求及提案解析附件，方便後續開發與版本管理。

## 📁 已保存到 GitHub 的內容

以下狀態已依 GitHub `main` 分支的實際檔案確認，並非僅依對話中的附件名稱推測。

| 來源／文件 | GitHub 檔案 | 狀態 |
|---|---|---|
| 期末專題提案作業規範.pdf | [期末專題提案作業規範.pdf](./myplan/期末專題提案作業規範.pdf) | ✅ 原 PDF 已上傳 |
| 專案提案解析.pdf | [專案提案解析.pdf](./myplan/專案提案解析.pdf) | ✅ 原 PDF 已上傳 |
| 專業摘要.pdf | [專業摘要.pdf](./myplan/專業摘要.pdf) | ✅ 原 PDF 已上傳 |
| Food Guardian 專題規劃（含四大核心亮點） | [Food_Guardian_Project_Plan.md](./myplan/Food_Guardian_Project_Plan.md) | ✅ Markdown 規劃文件已保存 |

## 📎 本次討論涉及、但尚未在 Repository 中找到的附件

下表列出的檔案曾用於本次專題討論或資訊圖表製作；**目前未在已檢查的 Repository 目錄中確認到原始檔**。它們並不等同於已保存的 Markdown 摘要。

| 來源附件 | GitHub 文字擷取檔 | 狀態 |
|---|---|---|
| A2Z outline example.pdf | — | ⏳ 原 PDF 尚未上傳 |
| Food Guardian_ Proposal Document.pdf | — | ⏳ 原 PDF 尚未上傳 |
| Food Guardian 專題提案資訊圖表 PNG（對話生成版本） | — | ⏳ PNG 尚未上傳 |

> **注意：** GitHub 上的 PDF 與 Markdown 是不同類型的檔案。這次只建立索引 README，沒有宣稱已完成所有 PDF 的文字擷取、檔案轉換或圖片上傳。

## 🧠 Food Guardian 四大核心亮點

| 編號 | 核心亮點 | 技術／功能重點 |
|---|---|---|
| **01** | **自然語言智慧互動**（Natural Language Interaction） | LLM 理解使用者的庫存查詢與餐點需求 |
| **02** | **自主式 AI Agent 決策**（Agentic Decision-Making） | Tool Calling、查詢庫存、食譜搜尋、可解釋推薦 |
| **03** | **食品安全情境感知**（Food Safety & Context Awareness） | 日期標示、保存條件、食品知識庫與規則檢查 |
| **04** | **數據驅動食材管理**（Data-Driven Food Management） | SQLite、Pandas、食材使用／丟棄／浪費比例分析 |

詳細規劃請參閱：[**Food_Guardian_Project_Plan.md**](./myplan/Food_Guardian_Project_Plan.md)。

## 🗂️ 目前檔案結構

```text
2026-11-11-DIC3-ProjectRefactor/
├── README.md                        # 本索引
└── myplan/
    ├── Food_Guardian_Project_Plan.md # 四大核心亮點、系統規劃與評估設計
    ├── 期末專題提案作業規範.pdf
    ├── 專案提案解析.pdf
    └── 專業摘要.pdf
```

## 🛠️ 專題預計使用的技術

- **介面：** Python、Streamlit
- **資料儲存：** SQLite
- **資料分析：** Pandas
- **智慧代理：** 具 Tool Calling 能力的 LLM
- **領域知識：** JSON 食品保存知識庫、Python 規則式檢查
- **推薦流程：** 庫存查詢 → 使用優先順序分析 → 食譜檢索 → 食安驗證 → 可解釋輸出

以上為**提案規劃**，不代表全部功能已在此 Repository 中實作。

## 📊 規劃中的驗證方式

| 項目 | 計畫 |
|---|---|
| 食材資料 | 約 20–30 種 |
| 食譜資料 | 約 20–30 道 |
| 情境資料 | 約 30 組 |
| Baseline | 不考慮家庭真實庫存的一般 LLM 食譜推薦 |
| Evaluation Metrics | Recipe Feasibility Rate、Inventory Matching Rate、Reminder Accuracy |
| 補充分析 | 食材使用量、丟棄量、浪費比例 |

**現階段屬 Proposal：** 不應將預期成效當作已驗證的實驗結果。

## ✅ 後續整理事項

- [x] 建立 Food Guardian 專題規劃 Markdown 文件
- [x] 索引目前 GitHub 中已有的 PDF 附件
- [x] 建立根目錄 README
- [ ] 上傳 A2Z 原始 PDF 與 Food Guardian Proposal 原始 PDF
- [ ] 上傳最終版本資訊圖表 PNG／PDF
- [ ] 視需求建立附件文字擷取版 Markdown（保留原始附件）
- [ ] 隨程式開發補充 `DESIGN.md`、安裝步驟與測試說明

---

**整理原則：** 原始檔保留以支援附件傳遞及核對；Markdown 方便 GitHub 文字搜尋、摘要與協作。檔案尚未上傳前，不以摘要或生成圖取代原始文件。
