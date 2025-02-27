# Git_example

## 目錄

- [Git初始化](#Git初始化)
- [Git日誌](#Git日誌)
- [Git重置](#Git重置)

## Git初始化

- Git 初始化
```
git init(後面省略為預設master(git init --initial-branch=main))
git remote add origin XXXX.git(git 網址)
```

- Git 添加所有更動至暫存區
```
git add .
git status .(確認沒紅字)//綠字=成功加入暫存區/紅字=未加入暫存區
```

- Git Commit "your commit"
```
git commit -m "Initial commit"
git status .(確認沒紅字)
```

- Git 上傳commit
```
git push -u origin master
```

- 整體流程
```
git init
git remote add origin XXXX.git
git add .
git status .
git commit -m "Initial commit"
git status .
git push -u origin master
```

## Git日誌
(**Q鍵離開**)
```
git log --all
```
```
git log origin --oneline
```

## Git重置 
### 請小心使用！！
- Git 查看 Commit 紀錄(**Q鍵離開**)
```
git log --oneline
```

- Git 退回 Commit (執行 log 查看, 取得對應commit id)
  - HEAD^ 表示「前一次」的意思，所以每一個 ^ 符號就會退回1次。
  - HEAD~ 表示「輸入要退回次數 (預設無輸入則1)」的意思，所以~3就是退回3次。
  - commit id 預設為--mixed。
    - --mixed (default) => 保留修改檔案(指的是工作區中的檔案)，並且撤銷全部暫存區檔案。(未追蹤的新檔案不納入)
    - --soft => 保留修改檔案(指的是工作區中的檔案)，並且不會撤銷暫存區檔案。(未追蹤的新檔案不納入)
    - --hard => 不保留修改檔案(指的是工作區中的檔案)，強制還原至指定 commit 有的檔案。(未追蹤的新檔案不納入)
```
git reset HEAD^
git reset HEAD~1
git reset 04601b2

git reset HEAD^^ --soft
git reset HEAD~2 --hard
git reset 04601b2 --mixed
```

## Git 文件大小寫問題

- 也可至config檔案修改(ignorecase = false)
```
git config --local core.ignorecase false
```

## 參考文件

>https://hackmd.io/@UmEXPPDuRqO4GLkq657i-g/ryODc4aBt#Git-%E6%9A%AB%E5%AD%98%E5%8D%80-Add-Stage
