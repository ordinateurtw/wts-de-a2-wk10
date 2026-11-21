# WBS-07B｜真實 API 執行與錯誤檢查紀錄

## 來源類型

本報告使用使用者提供的 Colab 實際執行截圖，並對照已提供的 v3.7 Notebook 程式碼。**目前沒有使用者最近幾輪的完整 Colab Run ZIP，因此以下不將不同輪次合併為一個假想的完整成功案例。**

## 已觀察的實測事件

| 事件 | 擷取自截圖 | 觀察結果 | 裁決 |
|---|---|---|---|
| API 真實產生教材 | `E01_API_200.png` | `02_GENERATE`，Groq `openai/gpt-oss-120b`，HTTP **200**；產出 10 頁標題及 Wiki ID | **PASS：API 已實際執行** |
| 異常格式 | `E02_Schema_Error.png` | 模型返回的 `slides` 含字串項目，未檢查型別便對 `s.get()` 操作，產生 `AttributeError` | **FAIL：Schema Gate 不足** |
| 頁數不足 | `E03_G2_9of10_429.png` | `G2_CONTENT FAIL`，顯示 `頁數 9 不等於設定的 10` | **FAIL：G2 正確攔截** |
| 修復成本過高 | `E03_G2_9of10_429.png` | 接續 `REPAIR_1` 對 `openai/gpt-oss-120b` 發出請求，HTTP **429** | **FAIL：原修復策略與 Token 配額衝突** |
| 動態主題 | `E04_Three_Topics.png` 等各輪畫面 | 已觀察就醫、交通、購物三個不同教材主題；不代表 70 輪皆不重複 | **PASS：至少三種主題產出有畫面證據** |
| Wiki 到 HTML 對應 | `E05_HTML_Slide.png` | 購物簡報含 `Wiki: DE-W06` 及 `DE-SRC-005 / 006` 來源標籤 | **PASS：特定頁面可追溯** |

## 三個重點：先前失敗、程式調整、目前證據

1. **Schema 型別錯誤**：生成後先做型別觀察，再由 G2 驗證每個 slide 是否為 `dict`、是否有 `title`、`wiki_ids`、`points`、`german_examples` 等欄位，未通過則修復或阻擋。
2. **9/10 頁**：G2 可攔截不足頁數。v3.7 程式新增 `FILL_MISSING` 增量修復，規劃 9+1 而不是整套重生。**尚缺同一次修復呼叫成功截圖，不把它標成實測 PASS。**
3. **HTTP 429**：程式 `groq_json()` 已有依 API 回傳延遲等待的邏輯，至多額外三次重試；原截圖中的 HTTP 429 是修復前的失敗證據，**不能冒充退避後成功**。

## 若老師要求「同一次完整執行的原始紀錄」

請從 Colab 最近成功的一輪下載 `wk10_colab_run_<run_id>.zip`，從中選取下列 **不含金鑰** 的檔案作為附錄或教師唯讀檔案：

- `lesson_plan.json`：該輪的主題、選用 Wiki、規劃大綱。
- `retrieved_wiki.json`：該輪 Wiki 證據。
- `accepted_deck.json`：通過 Gate 的投影片內容。
- `audit.json`、`run_summary.json`、`novelty_report.json`：執行結果、HTTP 狀態與跨輪檢查。

**注意**：原始 `01_PLAN_request.json` 或 `02_GENERATE_request.json` 可能含有來源摘錄與情境內容；可審核後再視必要提供，不須公開整份 ZIP。所有執行紀錄應避免貼出 Secret、Authorization Header 或不可公開的教材頁面。
