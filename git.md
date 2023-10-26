# git

配置基本信息：

    git config --global user.name "here-write-your-name"
    git config --global user.email  here-write-your-email

  
刷新/创建全新的仓库，需要用Git管理的项目的根目录执行：  

    git init
  

克隆项目：  

    git clone here-write-link-address

  
查看状态：

    #查看制定文件状态
    git status [文件名]
    
    #查看所有文件状态
    git status
  
与仓库连接：

    git remote add origin 'github仓库链接'

拉取：  
（远程仓库发生更改时需要合并）  
（本地分支  落后于远程仓库时无法提交需要先pull）

    git pull origin main

拉取远程和本地产生冲突时，可以用

    git config pull.rebase false
    #Git 会将远程分支的更新与你的本地分支进行合并，创建一个新的合并提交。使用合并策略可以保留分支的历史记录，每个分支的更改都能够保留在提交历史中。  
    
    git config pull.rebase true  
    #Git 会将你本地分支的提交应用于远程分支之上




添加所有文件到暂存区：

    git add . 
    # . 是该目录下所有的意思



提交暂存区中的内容到本地仓库 ：

    git commit -m "write-information"


推送：

    git push origin master/main 
    #据branch 而定


连接github已创建好的项目：

    git remote add  main https://github.com/rosettarosettarosetta/rosetta-s-tech-stack.git

查看远程仓库配置：

    git remote -v  
    
