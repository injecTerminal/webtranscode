项目部署文档
=
###  1. 前提环境
|   名称   |      版本       |
|:-------:|:---------------:|
| node.js | @8.12.0         |
| mysql   | @8.0.11 or @5.7 |
| linux   | @cenOS7         |
### 2. NodeJs 环境安装
<p align="center">
  <a href="https://nodejs.org/" title="点击链接" >
    <img
      alt="Node.js"
      src="https://nodejs.org/static/images/logo-light.svg"
      width="400"
    />
  </a>
</p>

```console
  //下载node压缩包
$ wget https://nodejs.org/dist/v10.15.1/node-v10.15.1-linux-x64.tar.xz
  //解压
$ tar xvf node-v10.15.1-linux-x64.tar.xz
  //转移系统用户目录下并重命名
$ mv node-v10.15.1-linux-x64 /usr/local/bin/nodejs
  //设置环境变量
$ echo PATH=$PATH/usr/local/bin/nodejs/bin >> ~/.bashrc
$ echo export PATH >> ~/.bashrc
  //最好先检查文件是否修改正常
$ tac ~/.bashrc
$ source ~/.bashrc
  //检查是否配置成功
$ node -v
$ v8.12.0
```
### 3. Mysql 安装部署
<p align="center">
  <a href="https://www.mysql.com/" title="点击链接">
    <img
      alt="MySql"
      src="https://dev.mysql.com/common/logos/mysql-logo.svg"
      width="400"
    />
  </a>
</p>

```console
  //下载mysql压缩包
# wget https://dev.mysql.com/get/Downloads/MySQL-8.0/mysql-8.0.11-1.el7.x86_64.rpm-bundle.tar
  //解压
# tar xzvf mysql-5.7.17-linux-glibc2.5-x86_64.tar.gz
  //转移系统用户目录下并重命名
# mv mysql-5.7.17-linux-glibc2.5-x86_64 /usr/share/mysql@5.7
  //设置软链接
# ln -s /usr/share/mysql@5.7 /usr/local/bin
# systemctl status mysqld.service
# systemctl start mysqld.service
# mysql --version
mysql  Ver 8.0.15 for Linux on x86_64 (MySQL Community Server - GPL)
  //获取临时密码
# grep 'password' /var/log/mysqld.log
# 2019-02-20T04:57:27.888761Z 5 [Note] [MY-010454] [Server] A temporary password is generated for root@localhost: 75LBtK;s1f8K
# mysql -uroot -p75LBtK\;s1f8K
  //修改临时密码
mysql> alter user 'root'@'localhost' identified by 'new_password';
mysql> exit
  //重启mysqld
# systemctl restart mysqld.service
# mysql -uroot -pnew_password
```
* 具体参见
  * __[MySQL@8.0](https://www.cnblogs.com/ruolin/p/9279944.html "链接")__
  * __[MySQL@5.7](https://blog.csdn.net/qq_40550973/article/details/80721014 "链接")__
