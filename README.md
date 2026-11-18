# 潔諾 Jessroin・委託進度

給委託人看的公開排單頁，加上只有管理員能進去的後台（進度看板、委託管理、歷史紀錄）。

## 檔案

| 檔案 | 用途 |
|---|---|
| `index.html` | 網站本體（版面、功能） |
| `data.js` | 委託資料。公開頁只放遮過的名字；完整資料用後台密碼加密，沒有密碼看不到 |
| `README.md` | 這份說明 |

## 第一次上傳到 GitHub Pages

1. 在 GitHub 建一個新的 repository，例如 `Jessroin-Commission-Queue`。
2. 按 **Add file → Upload files**，把 `index.html`、`data.js`、`README.md` 三個檔案拖進去，按 **Commit changes**。
3. 到 **Settings → Pages**，Source 選 **Deploy from a branch**，Branch 選 `main`、資料夾選 `/ (root)`，按 **Save**。
4. 等 1～2 分鐘，網址會是 `https://jessroin.github.io/Jessroin-Commission-Queue/`。

## 平常怎麼更新

GitHub Pages 是靜態網站，網頁沒辦法自己把資料存回 GitHub，所以更新分兩步：

1. 打開網站 → 右上角「後台登入」→ 輸入密碼 → 照常新增或修改委託。
   修改會先存在**這台裝置的瀏覽器**裡，後台上方會出現粉紅色提醒。
2. 按提醒旁邊的「下載 data.js」，把下載的 `data.js` 上傳到 GitHub repository，覆蓋舊的那個（Upload files → Commit changes）。
   上傳後等 1～2 分鐘，委託人看到的公開頁就會更新。

小提醒：

- 修改只存在你修改時用的那台裝置。換手機或電腦之前，先下載 `data.js` 上傳，另一台才會拿到最新資料。
- 清除瀏覽器資料會清掉還沒上傳的修改，改完記得盡快上傳。
- 每次關掉頁面或登出，再進後台都要重新輸入密碼。
- 密碼沒有寫在任何檔案裡。忘記密碼就解不開資料，請自己記好。
