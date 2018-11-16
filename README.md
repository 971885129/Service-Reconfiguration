# Service-Reconfiguration
服务器系统重装，重新配置
## 0.服务器IP设置
* 1.更换交换机。两台服务器所连接交换机由局域网迁到校园网交换机
* 2.更换IP，登陆服务器，设置相应的网口的IP地址，设置完成后，重启该网口即可

## 1.更改默认22端口
* 1.增加新端口

      vim sshd_config
      增加Port ****保存
* 2.重启sshd

      service sshd restart
## 2.增加用户

## 3.软件安装
### python
### yum
### 生信软件
### R
### openBLAS
    
