# Food Guardian｜專題規劃（Project Plan）

> 更新日期：2026-11-11  
> 階段：Proposal / 規劃文件（功能尚須依實際程式碼與實驗驗證）

## 01. 專題定位

**Food Guardian：結合領域知識與資料分析的智慧食材管理及家庭食物浪費減量 AI Agent**

目標：以實際家庭食材庫存為基礎，整合 AI Agent、食品保存領域知識與資料分析，協助使用者規劃餐點、優先利用現有食材、接收日期與保存提醒，並分析食材使用及浪費紀錄。

核心組合：**AI Agent + Domain Knowledge + Data Analytics + Real-world Application**。

## 02. 四大核心亮點

### 01 自然語言智慧互動（Natural Language Interaction）

- 透過日常語言查詢食材庫存、提出餐點需求與詢問保存資訊。
- LLM 理解使用者意圖，將需求轉換為庫存查詢、食譜搜尋等任務。
- 減少手動搜尋食譜與逐項比對庫存的操作。
- **情境示例**：「冰箱裡有雞蛋、番茄和快到期的牛奶，今天晚餐可以做什麼？」

### 02 自主式 AI Agent 決策（Agentic Decision-Making）

- 利用具備 Tool Calling 的 LLM，依需求呼叫庫存查詢、日期分析與食譜搜尋等工具。
- 結合資料與規則，判斷優先處理食材、產生建議並說明推薦理由。
- 不僅輸出一般食譜，也要核對真實庫存與必要條件。
- **情境示例**：系統查到番茄需優先使用，建議番茄炒蛋並註明食材是否足夠。

### 03 食品安全情境感知（Food Safety & Context Awareness）

- 同時考量日期標示類型、保存條件、實際庫存與使用者需求。
- 以 JSON 食品保存知識庫和 Python 規則提供有依據的提醒。
- 不僅根據日期就保證食材安全；保存情況不明時提醒進一步確認。
- **情境示例**：牛奶雖未超過標示日期，但若曾長時間未冷藏，仍提示確認保存狀況。

### 04 數據驅動食材管理（Data-Driven Food Management）

- 以 SQLite 儲存食材、數量、日期、使用與丟棄紀錄。
- 以 Pandas 分析使用量、丟棄量、浪費比例及庫存變化。
- 輔助辨識高剩餘或常被丟棄的食材，以改善餐點與採買安排。
- **情境示例**：分析發現葉菜類經常剩餘，建議先安排葉菜料理並調整採買數量。

### 四者之間的分工

| 核心亮點 | 核心問題 | 主要技術 |
|---|---|---|
| 01 自然語言智慧互動 | 使用者想做什麼？ | LLM、意圖理解 |
| 02 自主式 AI Agent 決策 | 系統如何執行？ | Agent、Tool Calling |
| 03 食品安全情境感知 | 在當下條件下，哪些建議適當？ | Domain Knowledge、JSON、Python 規則 |
| 04 數據驅動食材管理 | 有哪些資料與分析可支持決策？ | SQLite、Pandas |

**關鍵區分**：情境感知負責解讀當前食材條件與安全限制；數據驅動負責整理、統計與分析庫存及歷史資料。

## 03. 提案中的技術架構

1. **使用者與介面**：Streamlit，取得查詢與食材資料。
2. **Planner / Reasoning Agent**：具 Tool Calling 的 LLM，解析意圖與選擇工具。
3. **庫存資料層**：SQLite，管理食材名稱、數量、日期與使用紀錄。
4. **資料分析層**：Pandas，計算優先使用食材、消耗量、丟棄量與浪費比例。
5. **領域知識層**：JSON 食品保存知識及 Python 規則，處理日期標示、保存資訊與限制。
6. **食譜及決策層**：依現有庫存檢查候選料理可行性，產生建議及解釋。
7. **呈現與回饋**：食譜、提醒、分析圖表與使用／丟棄紀錄。

**概念流程**：自然語言需求 → Agent 任務分解 → 查詢庫存／食譜／保存知識 → Pandas 分析 → 食安與庫存規則檢查 → 可解釋推薦 → 使用紀錄回饋。

## 04. 實作優先順序（建議）

- [ ] P1：盤點既有 Repository 的實際模組與缺口（此文件建立時 Repository 尚為空）。
- [ ] P1：定義 SQLite 食材／食譜／使用紀錄資料表與初始資料。
- [ ] P1：實作庫存 CRUD、查詢工具與日期標示提醒。
- [ ] P1：建立可追溯食品保存 JSON 知識庫與規則檢查。
- [ ] P1：串接 LLM Tool Calling 與食譜候選搜尋／庫存核對。
- [ ] P2：以 Pandas 統計使用量、丟棄量與浪費比例，呈現圖表。
- [ ] P2：加入推薦理由、限制註記與不確定情況提示。
- [ ] P2：建立情境測試、基準方法比較與指標計算。
- [ ] P3：補充 README.md、DESIGN.md、測試說明與 Demo。

## 05. 評估規劃（提案值，非已完成結果）

- **Dataset**：約 20–30 種常見食材、20–30 道食譜、約 30 組家庭情境。
- **Baseline**：不考慮實際家庭庫存的一般 LLM 食譜推薦。
- **Metrics**：
  1. Recipe Feasibility Rate（食譜可行率）
  2. Inventory Matching Rate（庫存匹配率）
  3. Reminder Accuracy（日期提醒準確率）
- **補充分析**：使用量、丟棄量與浪費比例。
- **重要限制**：模擬情境的推薦改善不能直接推論真實家庭浪費已經下降；應以實測數據驗證。

## 06. 與課程規範的對應

Proposal 文件應涵蓋 Abstract、Introduction、Related Work（約 1/2 AI Technology + 1/2 Domain Know-how）、Deep Research（5 個 Mindsets、3 個 Controversies、10 個 Questions）、Proposed Scheme（Architecture、Flowchart、Pseudocode）及 References。

交付規劃：Proposal Document、Proposal PPT、GitHub Repository 與持續維護的 DESIGN.md；Final 另需程式碼、README、實驗結果、簡報與 Demo。

## 07. 目前狀態與下一步

本文保存的是**專題規劃與四大核心亮點**，並非已確認的功能實作清單。後續應以實際程式碼檢視實作完成度，再更新各項 Checkboxes、系統架構及測試結果。
