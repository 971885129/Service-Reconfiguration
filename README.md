# Service-Reconfiguration
服务器系统重装，重新配置
## 0.服务器IP设置
* 1.更换交换机。两台服务器所连接交换机由局域网迁到校园网交换机
* 2.更换IP，登陆服务器，设置相应的网口的IP地址，设置完成后，重启该网口即可
* 3.小服务器命令行设置IP

      #查看网络连接详情
      ifconfig
      #进入设置对应网卡目录
      cd /etc/sysconfig/network-scripts/
      #编辑指定网卡配置文件
      vim ifcfg-eth1
      #修改
      IPADDR=210.42.112.130
      GATEWAY=201.42.112.254
      DNS1=202.114.96.1
      NETMASK=255.255.255.0
* 4.打开第二个网卡，设置172IP
      
      编辑ifcfg-em2文件，增加IPADDR NETMASK GATEWAY
      
## 1.更改默认22端口
* 1.增加新端口

      vim sshd_config
      增加Port ****保存
* 2.重启sshd

      service sshd restart
## 2.设置用户和用户组
* 1.增加用户组

      groupadd manage
* 2.增加用户

      useradd:
            -g:设置用户所属用户组
            -d:设置用户主目录（一般设置在/home目录下）
            -m:若用户主目录不存在则创建（后不加参数）
            -G:指定用户附加组
      示例：
            useradd -g manage -d /home/username -m username 
* 3.设置密码
 
      passwd username
* 4.删除用户

      userdel username
* 5.设置用户工作目录属主和属组

      #修改/media/user/wxm/目录及目录下的所有文件的属主为wxm,属组为manage
      chown -R wxm.manage /media/user/wxm/
      #单独设置目录属组
      chgrp -R manage /media/user/wxm/
      #修改/media/user/wxm/目录及目录下所有文件的权限
      chmod -R 755 /media/user/wxm/
      #权限代表字符
      可读：r=4
      可写：w=2
      可执行：x=1
## 3.软件安装
### python
### yum
### 生信软件
### R
### openBLAS
    
