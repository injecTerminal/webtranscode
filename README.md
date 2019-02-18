项目部署文档
=
###  1. 前提环境
|   名称   |      版本       |
|:-------:|:---------------:|
| node.js | @8.12.0         |
| mysql   | @8.0.12 or @5.7 |
| linux   | @cenOS7         |
### 2. NodeJs 环境安装
<p align="center">
  <a href="https://nodejs.org/">
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
# wget http://dev.mysql.com/get/Downloads/MySQL-5.7/mysql-5.7.17-linux-glibc2.5-x86_64.tar.gz
  //解压
# tar xzvf mysql-5.7.17-linux-glibc2.5-x86_64.tar.gz
  //转移系统用户目录下并重命名
# mv mysql-5.7.17-linux-glibc2.5-x86_64 /usr/share/mysql@5.7
  //设置软链接
# ln -s /usr/share/mysql@5.7 /usr/local/bin
# systemctl status mysqld.service
# systemctl start mysqld.service
# mysql --version
```

