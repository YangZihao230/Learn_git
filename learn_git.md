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
    <!-- 新版本的分支是在提交后，再git branch <分支名字>创建 -->
git branch 3.0
<!-- 切换分支： -->
git checkout 2.0