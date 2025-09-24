# 学习地址：https://www.runoob.com/git/git-branch.html

# 简单实操
<!-- 获取git版本，验证安装 -->
PS D:\postgraduate\Traing_work\Git> git version
    >>git version 2.51.0.windows.1

<!-- 设置全局用户名，邮箱 -->
PS D:\postgraduate\Traing_work\Git> git config --global user.name "yzh"
PS D:\postgraduate\Traing_work\Git> git config --global user.email "1606803010@qq.com"

<!-- 初始化git,在当前目录下生成.git文件 -->
PS D:\postgraduate\Traing_work\Git> git init
Initialized empty Git repository in D:/postgraduate/Traing_work/Git/.git/

<!-- 临时暂存单个文件 -->
PS D:\postgraduate\Traing_work\Git> git add test.txt

<!-- 临时暂存当前目录所有文件 -->
PS D:\postgraduate\Traing_work\Git> git add .

<!-- git commit 提交保存，会打开vim编辑器，按a/i进入编辑，esc退出编辑，输入 英文":" +wq，保存并退出-->
PS D:\postgraduate\Traing_work\Git> git commit
    [master (root-commit) b84ef44] 第一次提交
    2 files changed, 0 insertions(+), 0 deletions(-)
    create mode 100644 learn_git.md
    create mode 100644 test.txt

<!-- 查询日志 -->
PS D:\postgraduate\Traing_work\Git> git log
    commit b84ef445d982bdaba99cef3e040cf2be5278b67e (HEAD -> master)
    Author: yzh <1606803010@qq.com>
    Date:   Wed Sep 24 14:18:20 2025 +0800

        第一次提交

<!-- 简化提交 -->
PS D:\postgraduate\Traing_work\Git> git add .
PS D:\postgraduate\Traing_work\Git> git commit -m "第二次提交"
    [master 5c70af6] 第二次提交
    1 file changed, 33 insertions(+)

<!-- 规范提交 -->
PS D:\postgraduate\Traing_work\Git> git add .
PS D:\postgraduate\Traing_work\Git> git commit -m "fix(learn_git.md): change content"
    [master aeb61bb] fix(learn_git.md): change content
    1 file changed, 6 insertions(+)

<!-- ！！！回退版本，!!! 删除回退之后的所有版本
git reset --hard <commit后的索引号>
    【例如：commit b3a8a9b5210bd7d1506c1f5a94e4a3e7f9994e4b (HEAD -> master)】
 -->
git reset --hard b3a8a9b5210bd7d1506c1f5a94e4a3e7f9994e4b

<!-- 不同版本的切换，分支功能branch,当前版本3.0 -->
git branch 1.0
...
git branch 2.0
git add .
git commit -m "3.0" 
    <!-- 新版本的分支是在提交后，再git branch <分支名字>创建
    这里是在2.0的分支上，创建了3.0
     -->
git branch 3.0
<!-- 切换分支\主流 -->
git checkout 2.0
git checkout master
git branch 

<!-- 将其他分支合并到当前分支：-->
git merge <branchname>

<!-- 上传到github仓库,最好是先添加好仓库再进行创作，或者克隆好仓库再修改上传 -->
    <!-- 创建主分支 -->
    git branch -M main
    <!-- 添加远程仓库地址 -->
    git remote add origin https://github.com/YangZihao230/Learn_git.git
    <!-- 上传到网盘（远程仓库） -->
    git push -u origin main
    <!-- 拉取远程仓库分支 -->
    <!-- 从远程仓库下载新分支与数据： -->
    git fetch origin main
    git pull origin main