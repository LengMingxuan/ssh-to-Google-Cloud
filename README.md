# ssh-to-Google-Cloud
How to ssh to Google Cloud
## 修改配置
### 1.先选择从浏览器打开ssh连接服务器
连接登录成功后，输入以下命令

sudo -i  #切换到root
passwd   #修改密码
然后会要求输入新密码，然后再重复一次密码，输入密码的时候不会显示出来，所以直接输入密码，然后回车，再然后重复输入密码回车。

修改root密码完成

### 2.接着修改SSH配置文件/etc/ssh/sshd_config
```$
vi /etc/ssh/sshd_config #编辑文件
```
找到以下内容并修改
```$
PermitRootLogin yes //默认为no，需要开启root用户访问改为yes
PasswordAuthentication yes //默认为no，改为yes开启密码登陆
```
修改完成后，再下按 esc 键，然后再输入
```$
:wq   #保存并退出
```
### 3.最后重启下服务器即可
```$
reboot    #重启服务器
$$$
如无法连接可以查看下防火墙规则

