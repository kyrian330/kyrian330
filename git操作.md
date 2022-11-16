1.配置用户名、邮箱

```
git config --global user.name "xxx"
git config --global user.email "xxx@qq.com"
```



2.生成 ssh key （默认路径 回车、不设密码 回车、再次回车 确认无密码）

```
ssh-keygen -t rsa -C "xxx@qq.com"
```

------



3.初始化本地仓库（将本地仓库变成受 git 管理的仓库）

```
git init
```

4.将单个文件添加到仓库（其实是先添加到缓存区）

```
git add test.md
```

5.或者用一个点，把当前目录下所有未追踪过的文件全部添加到缓存区 

```
git add .
```

6.将缓存区的文件提交到仓库，引号里面是本次提交的注释和说明

```
git commit -m '提交了文件'
```

---

做完 3、4、5、6之后，本地仓库就建好了。



7.远程关联 github 仓库

```
git remote add origin 'github上某个仓库的ssh'
```

例如

```
git remote add origin git@github.com:'username'/'repositories'.git
```



8.上传本地代码到 master 分支

```
git push -u origin master
```

输入 yes，再回车，代码推送成功





9.切换分支，先将 main 分支的数据下拉到本地（执行命令后，本地仓库的内容全部被 main 分支内容更换）

```
git pull origin main
```



切换到 main分支

```
git checkout main
```



示例，将本地仓库下的index.html，提交到main

```
git add index.html
```

```
git commit -m "提交了一份文件"
```

```
git push -u origin main
```



10.删除某个文件。

假设删除库里的 test.md。--cache表示不删除本地仓库内容

```
git rm -f --cache test.md
```

本次操作的说明

```
git commit -m '删除了 test.md'
```

提交（提交命令失效的话可以试试 在最后加个 -f ）

```
git push -u origin main
```



11.删除某个文件夹以及文件夹里的内容

​		先在本地创建一个 img 文件夹，里面放入一些图片，然后把 img 提交到 main 分支，提交三部曲上面已经介绍过了。

```
git add img
```

```
git commit -m '上传了一份 img 文件夹'
```

```
git push -u origin main
```

​		有时候会报错Please make sure you have the correct access rights and the repository exists.是因为网络问题，无法连接到GitHub仓库，多在网页上刷新几次就好。



删除 img 文件夹（注意这里是 -r ）

```
git rm -r --cache img
```

```
git commit -m '尝试删除 img 文件夹'
```

```
git push -u origin main
```

操作完毕。











