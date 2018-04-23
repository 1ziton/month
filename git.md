# Git 

## Git 工作流

[Git 工作流程](http://www.ruanyifeng.com/blog/2015/12/git-workflow.html)


## Git 与 SVN 区别

- [git和svn的详细对比](https://www.cnblogs.com/dazhidacheng/p/7478438.html)


## 如何正确提交PR

##### 1.1 如何发起 `pull request`

推荐 `GitHub` 使用工具，建议 [[WebStorm][webstorm-download]]() , [[Sourcetree][sourcetree-download]]() ，命令行( window 加强 `CMD` 工具 [[Cmder][cmder-home]]() ，建议不要下载那个客户端。

- [GitHub 如何创建 pull 请求](https://git.1ziton.com/waylau/github-help/blob/master/Creating%20a%20pull%20request%20%E5%88%9B%E5%BB%BA%20pull%20%E8%AF%B7%E6%B1%82.md)
- [GitHub 的 pull request 是指什么意思？](https://www.zhihu.com/question/21682976)
- [利用 WebStorm 来管理你的 GitHub](http://www.mrfangge.com/how-to-use-webstorm-to-manage-your-github/)
- [使用 WebStorm 上传代码到 GitHub](http://www.jianshu.com/p/752613f4b1c9)
- [Git本地项目上传 & SourceTree & GitHub 简单使用](http://www.blogs8.cn/posts/Au2te07)
- [GUI for Git|SourceTree|入门基础](http://www.jianshu.com/p/be9f0484af9d)
- [SourceTree 使用](http://blog.sina.com.cn/s/blog_a3c770670102uywk.html)
- [Git工作流的最佳实践总结](https://www.jianshu.com/p/202de00f267f)

##### 1.2 如何提交：

整个流程（以下举例，其中我为`giscafer`用户）：
我先 `fork` 了 `scm2/scm2-platform` 的仓库，然后我从我的仓库克隆到本地修改，修改完后提交到我的仓库，然后我再申请 `pull request` ，`scm2/scm2-platform` 同意合并后其实整个过程就完了，但是 `scm2/scm2-platform` 经常会有更改就需要我刚那一步在我本地同步一下你的远程仓库，同步后再提交到我的仓库。
具体代码:
```bash
# 列出远程仓库 URL
$ git remote -v
# List the current remotes （列出当前远程仓库）
# origin  https://git.1ziton.com/user/scm2-platform.git (fetch)
# origin  https://git.1ziton.com/user/scm2-platform.git (push)

# 设置一个新的远程仓库
$ git remote add 1ziton git@git.1ziton.com:scm2/scm2-platform.git

# 再次列出远程仓库 URL
$ git remote -v
# 1ziton     git@git.1ziton.com:scm2/scm2-platform.git (fetch)
# 1ziton     git@git.1ziton.com:scm2/scm2-platform.git (push)
# origin      git@git.1ziton.com:giscafer/scm2-platform.git (fetch)
# origin      git@git.1ziton.com:giscafer/scm2-platform.git (push)

# 获取上游代码
$ git fetch 1ziton

# 检查你的 fork’s 本地 master 分支，如果不在 master 分支就切换到该分支
$ git checkout master
# Switched to branch 'master'

# 合并来自 1ziton/master 的更改到本地 master 分支上。
$ git merge 1ziton/master
```

##### 1.3 提交之后：

提交合并到 `scm2/scm2-platform` 之后，为了保证与主仓库代码的一致性，还需要进行一次本地与远程仓库的手动更新。

- [如何同步 Github fork 出来的分支](http://jinlong.github.io/2015/10/12/syncing-a-fork/)
- [GitHub 同步 fork 别人的项目到自己的仓库](https://segmentfault.com/a/1190000003703918)



## 资源

- [awesome-github](https://giscafer.gitbooks.io/front-end-manual/content/devtool/awesome-github.html)
- [【视频】版本管理工具介绍—Git篇](https://www.imooc.com/learn/208)
- [【软件操作教程】SourceTree使用教程](https://www.cnblogs.com/soundcode/p/7205295.html)


## Git命令大全

详细阅读文章：[Git速查表](http://blog.csdn.net/halaoda/article/details/78661334)

**Git速查表**

![速查表](https://files.jb51.net/file_images/article/201409/git_big_jb51.jpg)


## git rebase 合并提交（修改已提交信息）

比如Github上的开源项目，要严格要求，一个功能点`feat`或者，一个`bug`修改，代码修改好，测试没问题，一次性提交修改的文件（只允许一个commit）

举例一个PR中commit两次的操作，然后工程维护者建议修改提交信息重新PR：https://github.com/NG-ZORRO/ng-zorro-antd/pull/78


[多个commit 需要合并为一个完整的commit提交](https://www.cnblogs.com/wangiqngpei557/p/5989292.html)

## 规范性的PR约束

commit 信息不是乱填的，PR 标题也不是乱填的。可以参考开源工程的一些约束说明：[CONTRIBUTING.md](https://github.com/NG-ZORRO/ng-zorro-antd/blob/master/CONTRIBUTING.md)


[webstorm-download]:https://www.jetbrains.com/webstorm/
[sourcetree-download]:https://www.sourcetreeapp.com/
[cmder-home]:http://cmder.net/
[coding-copy-writing]:https://open.coding.net/copywriting.html
