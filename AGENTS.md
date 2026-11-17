# AGENTS.md — 互動藝術實驗筆記

## 專案定位
一個可持續擴充的互動藝術研究筆記網站，整理音樂視覺化、肢體互動、創意程式等實驗。**未來新增文章只需編輯資料檔，不要重寫首頁。**

## 技術與結構
- HTML5 + CSS3 + 原生 JavaScript，無打包工具與後端，可直接使用瀏覽器開啟 `index.html`，亦可部署 GitHub Pages。
- `index.html`：首頁與文章容器；`assets/style.css`：粉彩插畫視覺與響應式設計；`assets/app.js`：搜尋、分類、卡片、文章與路由；`assets/illustrations/`：本地 WebP 插畫；`data/entries.js`：**內容的唯一來源**；`README.md`：操作與部署。
- GitHub Pages 支援專案子目錄；請使用相對路徑。

## 設計視覺規範
- 風格為溫柔手繪、水彩與粉彩插畫感，米白底色、柔紫、薄荷綠、淺粉色，圓角卡片與細緻陰影。
- 插畫可以有植物、音符、魚群、星點等創作主題，但不要過度擁擠；文字必須清晰可讀。
- 使用台灣繁體中文；保留桌機雙欄、手機單欄卡片與可操作的鍵盤焦點。
- 不要用整張頁面截圖冒充網頁；導航、文章、分類及搜尋必須是真正 HTML 互動功能。

## 新增文章規則
只修改 `data/entries.js` 內 `window.ART_NOTES = [...]` 的陣列，新增一個物件：
```javascript
{
  "id": "new-interaction-note",
  "title": "新的互動藝術筆記",
  "category": "創意程式",
  "date": "2026-11-17",
  "summary": "一到兩句簡介新的互動實驗與研究方向。",
  "tags": ["JavaScript", "互動"],
  "status": "概念",
  "sections": [
    {"heading": "設計目的", "body": "說明研究動機與使用情境。"},
    {"heading": "互動方法", "body": "說明輸入、處理與視覺輸出。"}
  ]
}
```
- `id` 使用不重複的英文小寫連字號，發表後不要更改。
- `category` 只能用「音樂視覺化」「肢體互動」「創意程式」。
- `date` 格式 `YYYY-MM-DD`；`status` 限「概念」「原型」「完成」。
- `tags` 建議 2–4 個；`sections` 至少 2 段，每段有 `heading` 和 `body`。
- 所有文字為純文字，不插入 HTML；避免宣稱尚未完成的研究結果。
- 新文章如沒有獨立插畫，目前使用預設插畫；若要提供獨立插畫，新增 `assets/illustrations/<slug>.webp`，在 `assets/app.js` 的 `artwork` 對照表補上即可。

## AI 開發流程
1. 先讀本文件、`README.md` 和 `data/entries.js`，確認資料規格。
2. 只是新增筆記時僅增加 `ART_NOTES` 內容；不能刪除既有資料或重新設計頁面。
3. 確認語法、`id` 唯一性、日期與分類合法，文章自然出現在列表。
4. 測試分類、搜尋、文章閱讀、返回、`#entry/<id>` 直接連結與手機版排版。
5. 只有修改視覺或功能才改 CSS/JS；涉及資料 schema 變動時同步更新本文件與 README。
6. 用 `textContent` 輸出筆記內容，避免把資料以 `innerHTML` 注入；不新增 API 金鑰或追蹤服務。

## 驗收條件
雙擊 `index.html` 即可看到網站；搜尋分類正常，文章可閱讀；在 GitHub Pages 也能公開瀏覽。新增一篇合法資料後，不必修改 HTML 即能自動顯示。
