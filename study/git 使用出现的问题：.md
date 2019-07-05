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

