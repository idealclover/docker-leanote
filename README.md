# Docker-leanote

leanote 蚂蚁笔记(v2.6.1) Docker部署

Thanks to [n3uz/docker-leanote](https://github.com/n3uz/docker-leanote)

### 部署

```
cd docker-leanote/docker
docker build -t idealclover/leanote .
docker run -d -p 9000:9000 --name leanote idealclover/leanote
```

文件在docker内的路径：

```
/usr/local/bin/leanote/conf : 配置文件存放路径
/usr/local/bin/leanote/public : 公共资源存放路径
/usr/local/bin/leanote/db_data : 数据库文件存放路径
```

构建时可通过 -v参数进行重定向

example:

```
docker run -d \
    -v ~/leanote/conf:/usr/local/bin/leanote/conf \
    -v ~/leanote/public:/usr/local/bin/leanote/public \
    -v ~/leanote/mongo:/usr/local/bin/leanote/db_data \
    -p 9000:9000 \
    --name leanote \
    idealclover/leanote
```

### 访问

`http://ip:9000`
