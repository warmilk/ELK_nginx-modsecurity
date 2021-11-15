`docker build -t my-modsec .` 

--tag 用于配置 image 的别名，-t 是 --tag 的缩写



`docker run -d -v /home/quyingVulHub/owasp-modsecurity/public-html/index.html:/usr/share/nginx/html/index.html -v /home/quyingVulHub/owasp-modsecurity/default.conf:/etc/nginx/conf.d/default.conf -p 80:80 -p 443:443 --name crs my-modsec` 

--name 用于配置 container 的别名

-d 是在后台运行的意思，不加 -d 会在前台运行，前台运行时候，会阻塞住终端里别的进程

-v 是挂载数据卷（宿主机：容器内）

-p 是端口（宿主机：容器内）






`docker ps -a` (process status 进程状态， -a 是 all 的意思)

`docker exec -it crs bash` （进入名为crs的container的内部执行bash命令, -t 是分配一个伪tty，也就是伪终端，tty就是打字机。-i是input的意思，就是为了保持接收输入的数据流）


`docker stop crs`

`docker restart crs`


`docker logs -f crs` (-f是follow的意思，打印crs的日志)

`docker logs -f crs --tail 100` (--tail 100 是查看最后100条的意思)

`docker logs -f crs --tail 100 | grep error`

`docker rm crs -f` (f是暴力force的意思，暴力删除container就不用先stop后删除)

======================================

`ll` 代替 `ls`

`docker images` 代替 `docker image ls`