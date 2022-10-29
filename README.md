# Git 操作參考流程
### git 做更改都要建一個 branch
### 創建 branch 的指令
### git branch newBranch1
### 新增完 branch ，要轉移過去
### 轉移 branch 的指令
### git checkout newBranch1
### 查看目前有什麼分支的指令
### git branch => 本地有什麼分支
### git branch -v => 包含遠端有什麼分支
### 然後可以進行更改，或是新增程式碼，在這個 branch 上，
### 如果想查看，已經改了什麼，查看修改的指令
### git diff

---
## 一樣在 newBranch1 上
## 要 commit 的流程
### 要看目前狀態的指令，會告訴你在哪一個 branch ， 跟有什麼檔案變更，
### 需要加到 staged 裡面，紅色是還沒用 add ， 綠色是已經 add 到 staged，
### git status
### 要把變更的加到 staged 裡的指令
### git add [檔案名稱]
### git add . => 全選加入
### 建立一個 commit 的指令，每一個 commit 要符合規範
### git commit -m "[feat:做了什麼變更]" -m"[how:怎麼去修改]"
### 想看 commit 的記錄的指令
### git log
### 按 Q 可以跳出 git log
### 當做完要在這個 branch 上新增的功能後
### 就把現在這個 branch push 到 github
### push 到遠端儲存庫的指令，在遠端庫也新增一個 branch 的概念
### git push [遠端儲存庫的連結] newBranch1
---
## 去到 github 頁面
### 當 push 上 github 後 ， github 會出現 pull request 的 message (綠色的 button )
### 按下去，就可以選擇將剛剛新增的 branch ， 合併到原本的主分支，
### 右邊是剛剛新增的 branch ，左邊是主要分支 branch
### 將兩個合併，選擇要留下更改的部分，merge 完之後，
### 就可以把 github 剛剛新增的 branch 刪除了
---
## 回到 VSCODE
### 先切換回本地端的主分支
### git checkout master
### 接下來把剛剛在 github merge 好的主分支 pull 下來， 下載回本地端
### git pull origin master
### 可以檢查 commit 紀錄是否有 merge 過，
### git log
### 然後本地端的 newBranch1 已經合併過了，所以可以把他刪除
### git branch -d newBranch1
### git 流程
---
## Git 補充指令
### git add [檔案名稱] 想要取消 add
### git reset -- [檔案名稱]  =>就可以把檔案移除 staged 區
### 當用 git branch -a => 會顯示遠端已刪除的分支
### 可以用 git fetch -p =>這樣不會顯示已刪除的遠端分支