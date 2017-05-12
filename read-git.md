# 1. 初始化git

- $ git init
- $ git config --global uesr.name 'jiangtao'
- $ git config --global user.eamil '2210506955@qq.com'

# 2. 工作区 =》暂存区=》版本区
- $ git add ./ 
    + 把文件从工作区送到暂存区
- $ git status 
    + 查看当前状态 
        * 红色 就是工作区 
        * 绿色就是暂存区 
        * nothing to commit, working directory clean 在版本区
- $ git commit -m '版本号'
    + 把文件从暂存区送到版本区
### 当文件经过一次暂存区 可以直接提交到版本区
- $ git commit --all -m '版本号'

## * 工具
- $ git status 产看当前所在工作区域
- $ git log 查看当前所在版本以前提交记录
- $ git log --oneline 简洁版提交记录 
- $ git reflog 查看所有提交记录

# 3.提档
- $ git reset --hard Head~0
    + 所有提交版本成倒叙形成一个伪数组 0就是上一次提交的
- $ git reset --hard [版本号]
    + 可以通过版本号精确的回退到某一次提交时的状态
    + 每次提交都有对应的版本号
    
# 4.分支
- 默认是有一个主分支master
- $ git branch dev
    + 创建了一个dev分支
    + 在刚创建时dev分支里的东西和master分支里的东西是一样的
- $ git branch
    + 查看所有分支
    + 开头*就是当前分支
- $ git checkout dev
    + 切换到指定的分支,这里的切换到名为dev的分支
- $ git merge dev
    + 合并分支内容,把当前分支与指定的分支(dev),进行合并
    + 当前分支指的是`git branch`命令输出的前面有*号的分支
- 合并时如果有冲突，需要手动去处理，处理后还需要再提交一次.

### GitHub 
- <a href="https://github.com">https://github.com</a>
    + 不是git,只是一个网站
    + 只不过这个网站提供了允许别通过git上传代码的功能
- <a href="https://git.oschina.net/login">https://git.oschina.net/login</a> 码云官网

- 提交代码到github(当作git服务器来用)
- https方式上传代码
    +  $ git push [地址] master`推送 <span style="color: red">：上传</span>
        * 示例: `git push https://github.com/huoqishi/test112.git master`
        * 会把当前分支的内容上传到远程的master分支上

    +  $ git pull [地址] master`拉下 <span style="color: red">：下载</span>
        *  示例: git pull https://github.com/huoqishi/test112.git master
        *  会把远程分支的数据得到:(*注意本地-要初始一个仓储!*)

    + `git clone [地址]`
        * 会得到远程仓储相同的数据,如果多次执行会覆盖本地内容。

- ssh方式上传代码
    + 公钥 私钥,两者之间是有关联的。
    + 生成公钥,和私钥
        * `ssh-keygen -t rsa -C "xiaoming@sina.com"`
    ## push和pull操作
#先pull , 再push

- $ git remota add origin git@github.com:Jiangtao1994/1994.git
    + 声明 origin 
        * $ git push origin master
- $ git push origin -u master
    + 当我们在push时，加上-u参数，那么在下一次push时
        * $ git push
    - 我们只需要写上`git push`就能上传我们的代码。(加上-u之后，git会把
        当前分支与远程的指定的分支进行关联。git push origin master)