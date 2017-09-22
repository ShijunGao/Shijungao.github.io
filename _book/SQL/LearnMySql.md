#### 利用Doker实现局部安装MySql Server
参考链接：
> http://blog.knowncold.me/2017/09/16/docker-sql-server

>https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-configure-docker

Windows：
>*1、以下均使用管理员模式下的powershall或cmd*

>*2、Docker在windows上是运行在hyper-v上的，所以家庭版没有hyper-v是无法使用*

* 安装Doker
* 将Doker内存调制4GB
* 拉取镜像

  ``` bash  
  $ docker pull microsoft/mssql-server-linux  //部分地区需要翻墙——全局代理
  ```
* 运行镜像
``` bash  
//windows下将 ' ' 改为 " "
$ docker run -e 'ACCEPT_EULA=Y' -e 'MSSQL_SA_PASSWORD=<YourStrong!Passw0rd>' -e 'MSSQL_PID=Developer' --cap-add SYS_PTRACE -p 1401:1433 -d microsoft/mssql-server-linux
```
* 查看Doker容器
``` bash
$ docker ps -a
```
* 启动
``` bash
$ doker start e69e056c702d //container id 见上
```
* 链接到SQL Server
``` bash
$ docker exec -it e69e056c702d "bash"
```
* 本地链接
``` bash
$ /opt/mssql-tools/bin/sqlcmd -S localhost -U SA -P '<YourPassword>'
```
* 进行数据库操作
``` DDL
CREATE DATABASE
CREATE TABLE
SELECT * FROM
GO
QUIT
```
* 可视化工具链接
  * DataGrip
