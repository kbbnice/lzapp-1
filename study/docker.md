##### 部署gitlab

https://www.cnblogs.com/zuxing/articles/9329152.html

1. ```
   `docker pull beginor/gitlab-ce:11.0.1-ce.0`
   ```

2. 

通常会将 GitLab 的配置 (etc) 、 日志 (log) 、数据 (data) 放到容器之外， 便于日后升级， 因此请先准备这三个目录。

```
`mkdir -p /mnt/gitlab/etc``mkdir -p /mnt/gitlab/log``mkdir -p /mnt/gitlab/data`
```

`mkdir -p /mnt/gitlab/log`

`mkdir -p /mnt/gitlab/data`

3. 准备好这三个目录之后， 就可以开始运行 Docker 镜像了。 我的建议是使用unless-stopped 作为重启策略， 
   因为这样可以手工停止容器， 方便维护。

   完整的运行命令如下：

   ```
   `docker run \``    ``--detach \``    ``--publish 8443:443 \``    ``--publish 8090:80 \``    ``--name gitlab \``    ``--restart unless-stopped \``    ``-v /mnt/gitlab/etc:/etc/gitlab \``    ``-v /mnt/gitlab/log:/``var``/log/gitlab \``    ``-v /mnt/gitlab/data:/``var``/opt/gitlab \``    ``beginor/gitlab-ce:11.0.1-ce.0`
   ```

`--detach \`

`--publish 8443:443 \`

`--publish 8090:80 \`

`--name gitlab \`

`--restart unless-stopped \`

`-v /mnt/gitlab/etc:/etc/gitlab \`

`-v /mnt/gitlab/log:/``var``/log/gitlab \`

`-v /mnt/gitlab/data:/``var``/opt/gitlab \`

`beginor/gitlab-ce:11.0.1-ce.0`



4. ### 配置GitLab主机名

   1、修改/mnt/gitlab/etc/gitlab.rb

    把external_url改成部署机器的域名或者IP地址

   ```
   `vim /mnt/gitlab/etc/gitlab.rb`
   ```

![img](https://images2018.cnblogs.com/blog/1259802/201807/1259802-20180718144421797-1885319298.jpg)

将external_url 改成想要的ip和端口： 如： 

`external_url 'http://192.168.1.1:99'`





##### 下载一半中断了 ，重新下载提示报错： 

`docker: Error response from daemon: Conflict. The container name "/gitlab" is already in use by container "cb7001602f6e31d1403738b30bf2aeda575a215cb71b975a18bcf455a17af5c8". You have to remove (or rename) that container to be able to reuse that name.`

翻译为： 镜像已存在需要删除它，怎么删除呢？

1. 先查看当前镜像： `docker images`

   会看到所有镜像列表包含id

2. 根据镜像id删除： 

   `docker rmi dfdfd43443` 其中： dfdfd43443为id



##### 国内镜像配置： 

vim /etc/docker/