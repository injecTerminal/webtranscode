项目部署文档
==
###  1.前提环境
|   名称   |    版本    |
|:-------:|:---------:|
| node.js | @8.12.0以上|
| mysql   | @8.12以上  |
| linux   | @cenOS7以上|
### 2.NodeJs环境安装
```console
$ //下载node压缩包
$ wget https://nodejs.org/dist/v10.15.1/node-v10.15.1-linux-x64.tar.xz
$ //解压
$ tar xvf node-v10.15.1-linux-x64.tar.xz
$ //转移系统用户目录下并重命名
$ mv node-v10.15.1-linux-x64 /usr/local/bin/nodejs
$ //设置环境变量
$ echo PATH=$PATH/usr/local/bin/nodejs/bin >> ~/.bashrc
$ echo export PATH >> ~/.bashrc
$ //最好先检查文件是否修改正常
$ tac ~/.bashrc
$ source ~/.bashrc
$ //检查是否配置成功
$ node -v
$ v8.12.0
```
  
