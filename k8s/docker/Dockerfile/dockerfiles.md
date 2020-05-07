from 

COPY

WORKDIR  

RUN

EXPOSE

ENTRYPOINT

CMD

挂载目录











```shell
from docker.io/centos:8
MAINTAINER William-ZXS
RUN yum clean all
RUN yum install -y redis
RUN yum clean all
# RUN yum install -y redis && rm -f /var/lib/rpm/__db* && rpm --rebuilddb && yum clean all
RUN sed -i 's/^bind/#bind/' /etc/redis.conf
RUN sed -i 's/^daemonize yes/daemonize no/' /etc/redis.conf
RUN sed -i 's/^protected-mode yes/protected-mode no/' /etc/redis.conf

EXPOSE 6379

ENTRYPOINT ["/usr/bin/redis-server"]
CMD ["/etc/redis.conf"]
```





```shell

from docker.io/centos:8

RUN yum install -y redis  && yum clean all

COPY init.sh /usr/local/bin/
RUN ln -s usr/local/bin/init.sh / 
RUN sed -i -e 's/^bind[ ]*127.0.0.1/bind 0.0.0.0/' /etc/redis.conf
ENTRYPOINT ["init.sh"]

EXPOSE 6379
CMD ["/etc/redis.conf", "--daemonize", "no"]
```



# WORKDIR

格式为 `WORKDIR <工作目录路径>`。

使用 `WORKDIR` 指令可以来指定工作目录（或者称为当前目录），以后各层的当前目录就被改为指定的目录，如该目录不存在，`WORKDIR` 会帮你建立目录。

之前提到一些初学者常犯的错误是把 `Dockerfile` 等同于 Shell 脚本来书写，这种错误的理解还可能会导致出现下面这样的错误：

```docker
RUN cd /app
RUN echo "hello" > world.txt
```

如果将这个 `Dockerfile` 进行构建镜像运行后，会发现找不到 `/app/world.txt` 文件，或者其内容不是 `hello`。原因其实很简单，在 Shell 中，连续两行是同一个进程执行环境，因此前一个命令修改的内存状态，会直接影响后一个命令；而在 `Dockerfile` 中，这两行 `RUN` 命令的执行环境根本不同，是两个完全不同的容器。这就是对 `Dockerfile` 构建分层存储的概念不了解所导致的错误。

之前说过每一个 `RUN` 都是启动一个容器、执行命令、然后提交存储层文件变更。第一层 `RUN cd /app` 的执行仅仅是当前进程的工作目录变更，一个内存上的变化而已，其结果不会造成任何文件变更。而到第二层的时候，启动的是一个全新的容器，跟第一层的容器更完全没关系，自然不可能继承前一层构建过程中的内存变化。

因此如果需要改变以后各层的工作目录的位置，那么应该使用 `WORKDIR` 指令


