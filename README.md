# UniAi

UniAi 是協助大學生規劃學習任務的 AI 網站，介面使用台灣常見用語。包含任務導航、AI 即時回答、步驟式教學、Prompt 產生器、回答查證清單與學習流程。

## 需求
- Node.js 20 以上
- 可使用 Responses API 的 OpenAI API key 與可用額度。ChatGPT 訂閱不會自動包含 API 額度，API 可能另外計費。

## 在 Windows 執行
1. 解壓縮專案資料夾。
2. 在此資料夾的網址列輸入 `cmd`，按 Enter 開啟命令提示字元。
3. 執行 `npm install` 安裝相依套件。
4. 複製 `.env.example` 並命名為 `.env`。
5. 用記事本開啟 `.env`，將 `OPENAI_API_KEY` 改為自己的 API key；請勿分享或公開這個檔案。
6. 執行 `npm start`。
7. 開啟瀏覽器並前往 http://localhost:3000。

## API 設定
- `OPENAI_API_KEY`：你的 API key。
- `OPENAI_MODEL`：必須是你的 API 專案有權限使用的模型。預設使用 `gpt-5`；若帳戶沒有此模型權限，請改為 API 專案可用的模型 ID。
- `PORT`：網站使用的本機連接埠，預設為 3000。

## 安全與限制
- API key 僅存放在伺服器端 `.env`，不要放入 HTML，也不要上傳到 GitHub。
- 本版本是本機展示原型，尚未包含帳號、資料庫、每位使用者的使用額度或完整濫用防護。公開部署前應新增身份驗證、速率限制與成本控制。
- 對話歷史僅保存在目前瀏覽器頁面的記憶體中，重新載入後會清除。
- AI 可能會出錯。重要事實、數據與引用仍須自行查證。

## 著作權

© 2026 Xueerlian. 保留所有權利。


## Adaptive Prompt Engine (updated)

The Prompt Learning Lab now builds task-specific prompts for case studies, research, presentations, video scripts, data analysis, writing, translation, and exam preparation. Users can select:
- Current stage: starting, working, improving a draft, or final review
- Collaboration style: coach, thinking partner, assistant, or rigorous reviewer
- Depth: simple, detailed, or expert
- Interaction: ask clarifying questions, guide one step at a time, or provide structured output first

Changing any of these controls regenerates the prompt. The generated prompt includes a workflow specific to the selected task, quality-control requirements, and the user's context and output format. The prompt interface supports Traditional Chinese, Vietnamese, and English. This is a prompt-generation feature and does not require an API key; AI Assistant responses still require server-side API configuration.
