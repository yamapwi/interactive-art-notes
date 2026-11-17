# 互動藝術實驗筆記｜粉彩插畫版

一個以輕柔插畫視覺呈現音樂視覺化、肢體互動和創意程式實驗的靜態網站。

## 使用方式
直接用瀏覽器開啟 `index.html`，即可使用搜尋、分類與文章閱讀。所有插畫都在本地，首次載入字型需要網路，但無網路時會使用系統中文字型。

## 新增筆記
先閱讀 `AGENTS.md`，在 `data/entries.js` 的 `window.ART_NOTES` 陣列加入一個符合範例的新物件。網站自動產生文章卡片與 `#entry/<id>` 閱讀連結。

## GitHub Pages 發布
1. GitHub 建立 Public Repository，例如 `interactive-art-notes`。
2. 將本資料夾裡的 `index.html`、`assets/`、`data/`、`AGENTS.md`、`README.md` 上傳至 Repo 根目錄。
3. Settings → Pages → Build and deployment → Deploy from a branch → `main` / `(root)` → Save。
4. GitHub 提供公開網址後，確認首頁及每篇筆記可以正常點擊，並將真實網址補進作業 PDF。

## 檔案說明
- `index.html`：首頁與文章頁面模板
- `assets/style.css`：粉彩視覺、卡片與響應式排版
- `assets/app.js`：文章資料驗證、分類、搜尋與路由
- `assets/illustrations/`：插畫圖片
- `data/entries.js`：文章資料唯一來源
- `AGENTS.md`：讓 AI 可持續擴充的專案規範

插畫素材由生成式工具製作，並裁切成本站裝飾素材。網站 HTML 與資料內容可獨立編輯。
