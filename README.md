无需docker知识，简单执行一条命令即可编译、运行一个完整的漏洞靶场镜像。

## Installation

首先在Ubuntu 20.04下安装docker以及docker-compose:

```bash
# 安装pip
curl -s https://bootstrap.pypa.io/get-pip.py | python3

# 安装最新版docker
curl -s https://get.docker.com/ | sh

# 启动docker服务
systemctl start docker

# 安装compose
pip install docker-compose 
```

其他操作系统安装docker和docker-compose可能会有些许不同，请阅读Docker文档进行安装。

## Usage

```bash
# 下载项目
wget https://github.com/vulhub/vulhub/archive/master.zip -O vulhub-master.zip
unzip vulhub-master.zip
cd vulhub-master

# 进入某一个漏洞/环境的目录
cd flask/ssti

# 自动化编译环境
docker-compose build

# 启动整个环境
docker-compose up -d
```

每个环境目录下都有相应的说明文件，请阅读该文件，进行漏洞/环境测试。

测试完成后，删除整个环境

```
docker-compose down -v
```

本项目每个漏洞环境均附带文档，建议你购买1G内存的vps搭建漏洞测试环境，文档中所说的`your-ip`均指你的vps的ip地址，如果你是用虚拟机搭建测试环境，是指你的虚拟机IP，而不是docker容器内部的IP，请不要混淆。

**本项目中所有环境仅用于测试，不可作为生产环境使用！**

## Notice

注意事项：

1. 为防止出现权限错误，最好使用root用户执行docker和docker-compose命令
2. docker部分镜像不支持在ARM等架构的机器上运行

## Contribution

本项目依赖于docker，在编译及运行过程中出现的任意异常都是docker以及相关程序抛出的，请先自行查找错误原因。如果确定是因为Dockerfile编写错误（或代码错误）导致的，再联系我。