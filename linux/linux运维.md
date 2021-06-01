# Linux

## pyhton

```
py 编译为pyc -> python3 -m compileall {name}
```

## linux服务器互信

```
备注：让两台服务器互信（双方跳转登录不用输入口令）
1. 生成秘钥，并添加信任
我的环境中node1的ip是192.168.168.201，node2的ip是192.168.168.202.
[root@node1 ~]# ssh-keygen -t rsa -P '' -f ~/.ssh/id_rsa         #生成rsa
[root@node1 ~]# ssh-copy-id -i  ~/.ssh/id_rsa.pub root@192.168.168.202  #复制201的公钥到202机器上，这样就可以使用在201机器上免密码登录202机器了。

[root@node2 ~]# ssh-keygen -t rsa -P '' -f ~/.ssh/id_rsa         #生成rsa
[root@node2 ~]# ssh-copy-id -i  ~/.ssh/id_rsa.pub root@192.168.168.201  #复制202的公钥到201机器上，这样就可以使用在202机器上免密码登录201机器了。
注意：
　　如果远程主机的端口非22端口，需要指定-p port选项。
　　ssh-copy-id是由openssh-clients包提供，没有这个命令可以安装这个包。
     centos6,7使用ssh-copy-id的时候可以不用指定-i选项，centos5必须指定的。
```

