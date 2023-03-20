---
title: Hexo使用教程
date: 2023-03-20 14:29:41
tags:
---

#### 1.第一步安装[git](https://git-scm.com/download/win)和[node.js](https://nodejs.org/zh-cn/download)

<!--more-->

#### 2.本地新建名为blog的文件夹，进入文件夹，安装[Hexo](https://hexo.io/zh-cn/)
~~~
npm install -g hexo-cli
~~~

- 安装 Hexo 完成后，请执行下列命令，Hexo 将会在指定文件夹中新建所需要的文件。
~~~
$ hexo init
$ npm install
~~~
- 如果刚才没有在本地新建blog文件夹，则执行下列命令，可以同时创建文件夹
~~~
hexo init blog
cd blog
npm install
~~~
#### 3.运行一下看看是否成功
~~~
hexo s
~~~
#### 4.关联到github
[github](https://github.com)上创建名为blog的新仓库,注意仓库要是空的，不能有readme或者其他文件。
执行以下命令
~~~
git init  //在文件夹初始化本地仓库
git remote add origin https://github.com/username/blog.git //与GitHub上新建的远程仓库建立连接
git branch -M main  //切换分支，以前是master分支，由于"black lives matter"，改成了main，所以要切换
git add . //将该目录下所有文件添加到本地仓库
git commit -m"描述" //将刚刚添加的文件提交到本地仓库
git push -u origin main //把文件push到远程仓库的分支
~~~

#### 5.下载一个hexo主题，这里选择[Hipaper](https://github.com/iTimeTraveler/hexo-theme-hipaper)
- 将下载的主题解压放在themes文件夹下，改名为Hipaper
- 更改_config.yml文件里的theme为Hipaper
- hexo s生成以下看看
  
#### 6.部署到github pages
- 本地创建并切换分支
~~~
git checkout -b gh-pages
~~~
- 上面的指令也可以写为以下两条命令
~~~
git branch gh-pages //创建分支
git checkout gh-pages //切换分支
~~~
- 如果已经创建过分支，可以查看分支，并切换
~~~
git branch  //查看分支
git checkout gh-pages //切换分支
~~~
- 查看远程分支
~~~
git branch -r
~~~
- 远程仓库创建空的分支，该分支会包含父分支的所有文件，但新的分支不会指向任何以前的提交，就是它没有历史，如果你提交当前内容，那么这次提交就是这个分支的首次提交。
~~~
git checkout --orphan gh-pages
~~~
- 删除所有文件，获得一个空的分支
~~~
git rm -rf . //注意：最后的‘.’不能少
~~~
- 提交分支如果没有任何文件提交的话，分支是看不到的，所以我们需要创建一个新文件，然后提交则新创建的branch就会显示出来
~~~
echo '# new branch' >> README.md
git add README.md
git commit -m 'new branch'
~~~
- 最后push到远程仓库，则新的空分支就创建成功了
~~~
git push origin gh-pages
~~~
- 如果操作错了，可以删除远程分支，然后重来一遍
~~~
git push -d origin gh-pages
~~~
- 安装hexo-deployer-git插件，不然会报错：ERROR Deployer not found: git
~~~
npm install hexo-deployer-git --save
~~~
- 修改_config.yml文件里的url和deploy，最后执行以下指令完成部署
~~~
hexo d
~~~


