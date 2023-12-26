## 快速使用

1. 本地安装
   - `git`
   - `Docker`(系统需为Linux，Windows 10 Build 15063+，或MacOS 10.12+，且必须要 `64`位）
   - `docker-compose 1.7.0+`
2. `clone`项目：
   ```
   $ git clone https://github.com/yeszao/dnmp.git
   ```
3. 如果主机是 Linux系统，且当前用户不是 `root`用户，还需将当前用户加入 `docker`用户组：
   ```
   $ sudo gpasswd -a ${USER} docker
   ```
4. 拷贝并命名配置文件（Windows系统请用 `copy`命令），启动：
   ```
   $ cd dnmp                                           # 进入项目目录
   $ cp env.sample .env                                # 复制环境变量文件
   $ cp docker-compose.sample.yml docker-compose.yml   # 复制 docker-compose 配置文件。
   $ docker-compose up                                 # 启动
   ```
5. 在浏览器中访问：`http://localhost`
6. 远程调试php xdebug
   1. 本地(你自己的电脑)  打开终端 输入

      ```
      ssh -NR 9003:localhost:9003 root@59.110.33.116 -p 2222
      或者
      ssh -R 9003:localhost:9003 root@59.110.33.116 -p 2222

      区别是 -N 取消了终端链接, 只做接口转发 , 用户名和密码都是 root root , 端口只能是 9003, 要改的话请修改 services/php81/php.ini 中的 xdebug.remote_port = 9003
      ```
