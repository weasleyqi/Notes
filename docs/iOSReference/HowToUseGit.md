（1）git clone 服务器用户名@服务器IP:~/Git目录/.git
 
        功能：下载服务器端Git仓库中的文件或目录到本地当前目录。
 
（2）对Git目录中的文件进行修改。
 
（3）git status
 
        功能：查看Git仓库中的文件状态。
 
（3）git add .
 
        功能：向本地Git仓库中添加修改文件或目录。
 
（4）git commit -m "注释"
 
        功能：提交修改文件或目录到本地Git仓库。
 
（5）git pull
 
        功能：从服务器中的Git仓库中获取最新代码，并与本地代码自动merge，如果服务器中的代码与本地要提交的代码有冲突，冲突部分
                 会在文件中体现。
 
（6）git status
 
        功能：查看Git仓库中的文件修改状态。
 
（7） 如有冲突->修改。
 
（8） git diff
 
         功能：查看修改文件与本地Git仓库中的文件的异同，即：你修改了文件中哪些部分。
 
（9）git push
 
        功能：向服务器的Git仓库中提交本地Git仓库已修改的文件或目录。
 
知识点：
 
（1）git checkout .
 
        功能：从服务器的Git仓库中下载最新代码并覆盖掉所有本地文件，包括已经修改的。
 
（2）显示git配置项：
 
        git config --global --list
 
（3）配置用户名：
 
        git config --global user.name "用户名"。
 
（4）配置邮箱：
 
        git config --global user.email 邮箱。
 
（5）给命令配置别名：
 
        git config --global alias.co checkout
 
（6）显示某一版本更改详情：
 
        git show 版本号。
 
（7）查看修改日志：
 
        git log .
 
（8）git fetch：
 
        从远程服务器端获取最新版本到本地，不会自动与本地代码merge（git pull = git fetch + git merge）。