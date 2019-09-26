#### git 使用出现的问题：

一、当连接了一个不存在的，或者错误的远程仓库：

`zkyweb-ptyc.git`,

我的本意是添加到 `kbbnice` 下的`zkyweb-ptyc`仓库，然而少写了`kbbnice`:

```
git remote add origin git@github.com:kbbnice/zkyweb-ptyc.git

fatal: remote origin already exists.	//翻译：远程仓库已存在。

//origin 作为远程仓库在本地git中的名称。
```

此时连接了一个错误的仓库。

当这时候执行 `git push -u origin master`,会出现：

```
fatal: 'git@github.com/zkyweb-ptyc.git' does not appear to be a git repository
fatal: Could not read from remote repository.
```

此时如果重新填写正确的地址再连接：`git remote add origin git@github.com:kbbnice/zkyweb-ptyc.git`;

报错：（已经

```
git remote add origin git@github.com:kbbnice/zkyweb-ptyc.git

fatal: remote origin already exists.
```





#####  版本回退出现more问题

λ git reset --hard HEAD^
More?

这是因为cmd控制台中换行符默认是^，而不是\ ，所以它的more？的意思是问你下一行是否需要再输入，而^ 符号就被当做换行符而被git命令忽略掉了。

解决方法有如下几种：

```
git reset --hard "HEAD^"   //加引号
git reset --hard HEAD^^  //加一个^
git reset --hard HEAD~ 或者 git reset --hard HEAD~1  //把^换成~，~ 后面的数字表示回退几次提交，默认是一次
```



#### 版本回退命令： 

`git reset --hard HEAD~2 `  或者 `git reset --hard HEAD^^`代表回退上上个版本

`git reset --hard es13223` 用版本号回退（可以不把所有版本号打上只需要从头取几个就够了)



`git log --pretty=oneline`  把git log 每项一行展示



##### 版本回退后无法提交的问题：

1. git revert '版本号'
2. git push



