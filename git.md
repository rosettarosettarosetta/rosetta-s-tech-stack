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


添加所有文件到暂存区
    git add . 
    # . 是该目录下所有的意思


提交暂存区中的内容到本地仓库 
    git commit -m "write-information"



