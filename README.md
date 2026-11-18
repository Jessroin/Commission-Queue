# 潔諾 Jessroin・委託進度

給委託人看的公開排單頁，加上只有管理員能進去的後台（進度看板、委託管理、歷史紀錄）。

## 檔案

| 檔案 | 用途 |
|---|---|
| `index.html` | 網站本體（版面、功能） |
| `data.js` | 委託資料。公開頁只放遮過的名字；完整資料用後台密碼加密，沒有密碼看不到 |
| `README.md` | 這份說明 |

## 一、上傳到 GitHub Pages（只做一次）

1. 在 GitHub 建一個新的 repository（要選 Public）。
2. 按 **Add file → Upload files**，把 `index.html`、`data.js`、`README.md` 拖進去，按 **Commit changes**。
3. 到 **Settings → Pages**，Source 選 **Deploy from a branch**，Branch 選 `main`、資料夾選 `/ (root)`，按 **Save**。

## 二、做一把「存取權杖」（只做一次）

1. GitHub 右上角頭像 → **Settings** → **Developer settings** → **Personal access tokens → Fine-grained tokens → Generate new token**。
2. Repository access 選 **Only select repositories**，只勾這個網站的 repository。
3. Permissions 按 **＋ Add permissions** → 勾 **Contents** → 改成 **Read and write**。
4. 按 **Generate token**，複製 `github_pat_…`（只會顯示一次），也記下到期日。

## 三、在後台開啟自動更新（只做一次）

後台登入 →「委託管理 → GitHub 設定」→ 填帳號、Repository 名稱、分支 `main`、權杖和到期日 →「儲存並測試連線」。

之後每次在後台修改都會直接更新，約 1 分鐘後公開頁就會變。

## 小提醒

- 權杖會跟委託資料一起用後台密碼加密，不會以明碼存在任何檔案裡。
- 填上權杖到期日，到期前 14 天後台會提醒；過期或失效也會提醒你到「GitHub 設定」換一把新的。換好後按「重試」，期間的修改會補傳上去。
- 網站改版時，只要上傳新的 `index.html` 蓋掉舊的就好。**不要**用舊的 `data.js` 蓋掉 GitHub 上的，不然最新的委託資料會被蓋回舊的。
- 每次關掉頁面或登出，再進後台都要重新輸入密碼。
- 密碼沒有寫在任何檔案裡。忘記密碼就解不開資料，請自己記好。
