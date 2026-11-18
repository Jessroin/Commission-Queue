# 潔諾 Jessroin・委託進度

給委託人看的公開排單頁，加上只有管理員能進去的後台（進度看板、委託管理、歷史紀錄）。

## 檔案

| 檔案 | 用途 |
|---|---|
| `index.html` | 網站本體（版面、功能） |
| `data.js` | 委託資料。公開頁只放遮過的名字；完整資料用後台密碼加密，沒有密碼看不到 |
| `README.md` | 這份說明 |

## 一、上傳到 GitHub Pages（只做一次）

1. 在 GitHub 建一個新的 repository，例如 `Jessroin-Commission-Queue`（要選 Public）。
2. 按 **Add file → Upload files**，把 `index.html`、`data.js`、`README.md` 拖進去，按 **Commit changes**。
3. 到 **Settings → Pages**，Source 選 **Deploy from a branch**，Branch 選 `main`、資料夾選 `/ (root)`，按 **Save**。
4. 等 1～2 分鐘，網址會是 `https://jessroin.github.io/Jessroin-Commission-Queue/`。

## 二、做一把「存取權杖」（只做一次）

網站要靠這把權杖，才能在你修改後自動更新 GitHub 上的資料。

1. GitHub 右上角頭像 → **Settings** → 左側最下面 **Developer settings**。
2. **Personal access tokens → Fine-grained tokens → Generate new token**。
3. 填寫：
   - Token name：隨便取，例如 `委託進度網站`
   - Expiration：選最長的期限（到期後要重做一把）
   - Repository access：選 **Only select repositories**，只勾這個網站的 repository
   - Permissions → Repository permissions → **Contents** 選 **Read and write**
4. 按 **Generate token**，複製那串 `github_pat_…`（只會顯示一次）。

## 三、在後台開啟自動更新（只做一次）

1. 打開網站 → 右上角「後台登入」→ 輸入密碼。
2. 上方會出現「還沒設定 GitHub 自動更新」，按「設定」。
3. 填 GitHub 帳號（`jessroin`）、Repository 名稱、分支（`main`），貼上權杖，按「儲存並測試連線」。

完成後，之後每次在後台修改都會直接更新，約 1 分鐘後委託人看到的公開頁就會變。右上角會顯示「更新到 GitHub…」→「已更新」。

## 小提醒

- 權杖會跟委託資料一起用你的後台密碼加密，不會以明碼存在任何檔案裡。
- 權杖到期或失效時，後台上方會出現「GitHub 更新失敗」，到「GitHub 設定」換一把新的就好；在這之前的修改會先保存在這台裝置，換好後按「重試」。
- 每次關掉頁面或登出，再進後台都要重新輸入密碼。
- 密碼沒有寫在任何檔案裡。忘記密碼就解不開資料，請自己記好。
