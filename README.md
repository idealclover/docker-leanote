# Docker-leanote

leanote 蚂蚁笔记(v2.6.1) Docker部署

Thanks to [n3uz/docker-leanote](https://github.com/n3uz/docker-leanote)

### 运行

```
git clone https://github.com/idealclover/docker-leanote.git
cd docker-leanote/docker
docker build -t idealclover/leanote .
docker run -d \
    -v ~/leanote/conf:/usr/local/bin/leanote/conf \
    -v ~/leanote/public:/usr/local/bin/leanote/public \
    -v ~/leanote/mongo:/usr/local/bin/leanote/db_data
    -p 9000:9000 \
    --name leanote \
    idealclover/leanote
```
### 访问

`http://ip:9000`
