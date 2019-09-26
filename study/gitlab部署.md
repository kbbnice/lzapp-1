##### 参考地址：

https://blog.csdn.net/abcdad/article/details/80223355

##### 配置开放的ip和端口地址：

1. `vi /etc/gitlab/gitlab.rb`

2. `**gitlab-ctl reconfigure**`

3. `**gitlab-ctl restart**`



##### 修改密码

1. `su - git ` (切换到git账户)

2. `gitlab-rails console production` （进入git控制台）

   Loading production environment (Rails 4.1.1)

3. irb(main):001:0> `user = User.where(id:1).first` （获取用户id为1的用户）
   irb(main):002:0> `user.password='66668888'` （修改密码）
   irb(main):003:0> `user.save! `（保存， 如果成功会返回true)

 （参考链接： https://blog.csdn.net/bisal/article/details/54672184

https://www.cnblogs.com/sunky/articles/6196312.html）





##### gitlab下载地址（清华大学）

https://mirrors.tuna.tsinghua.edu.cn/gitlab-ce/yum/el7/



##### 汉化教程

https://www.jianshu.com/p/2400d9e57fd1

