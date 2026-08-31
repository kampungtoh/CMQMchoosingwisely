# CMQM Choosing Wisely 輸血明智選擇 民眾衛教

奇美醫療財團法人奇美醫院 品質管理部

## 內容

| 檔案 | 說明 |
|---|---|
| `index.html` | 衛教主頁（八語言、入站前測、四種血品、有 7 就好、閾值表、替代方案、常見問題、捐血數據、進入遊戲入口）|
| `chimei-transfusion-game.html` | 輸血明智選擇 闖關遊戲（後測）。會讀取網址參數 `rid`、`src`、`lang` 沿用同一個 response_id |
| `chimei-transfusion-survey.html` | 成效評估問卷（前後測）|
| `chimei-transfusion-dashboard.html` | 成效儀表板原型（示範資料）|
| `.nojekyll` | 讓 GitHub Pages 不經 Jekyll 處理 |

## 動線

主頁入站前測 → 衛教內容 → 「進入輸血闖關遊戲」按鈕（自動帶 `?src=orbs&rid=<id>&lang=<語言>`）→ 遊戲沿用同一個 response_id 作為後測。

## 資料收集（尚未接）

主頁與遊戲的 JavaScript 頂端各有一個 `ENDPOINT` 變數，目前留空（留空時只在瀏覽器 console 記錄，畫面照常運作）。接好後端（Google Apps Script / Supabase / PostgreSQL 等）後，把兩個檔的 `ENDPOINT` 填成同一個接收網址並重新部署，前後測即可用 `response_id` 配對。

本頁只放匿名衛教資料，請勿加入任何可識別個資。

## 部署為 GitHub Pages

1. 把本資料夾所有檔案（含 `.nojekyll`）放到 repo 根目錄後 push。
2. GitHub repo → Settings → Pages → Build and deployment → Source 選 **Deploy from a branch**，Branch 選 `main`、資料夾 `/ (root)`，Save。
3. 約一分鐘後網址為 `https://kampungtoh.github.io/CMQMchoosingwisely/`。

## 待辦（部署後）

- 捐血六項數據上線前與台灣血液基金會官方數字核對。
- 日、韓、越、印、泰醫療翻譯請母語或專業醫療翻譯校對。
- 決定後端並回填 `ENDPOINT`。
