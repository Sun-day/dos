# dos

## 安全基础入门之windows dos基础入门
```
创建文件 
md D:/file
设置文件夹级别  h 隐藏  a 所有用户  s 系统文件
attrib +h +a +s D:/file
输出指定内容到文件
echo aaa>aaa.txt
查看文件内容
type aaa.txt
分页显示内容 
type aaa.txt | more

输出多行到指定文件
copy con aaa.txt
保存退出
ctrl+z 回车 

删除文件
del aaa.txt
移动文件
move D:/aaa.txt C:/aaa.txt
修改文件名
ren  C:/aaa.txt C:/bbb.txt
修改关联
assoc .txt=exefile
修正关联
assoc .txt=txtfile
创建文件并指定文件占用磁盘大小
fsutil file createnew  c:/system/aaa.ini 123123123
关机 c显示重启提示  t时间 s关机 r重启  f强制 l注销 a取消
shutdown  -s -t 1100 -c '小垃圾去死吧'
注销
logoff 
shutdown -l

查看本机开放的端口
netstat -an
telnet: 23
RDP: 3389
TCP共享服务：445



```

# windows 进阶之批处理

```
输出空行
echo.

修改窗口显示名称
title 

屏蔽过程
@echo off

判断
if "%num%"=="1"

暂停
pause

定义可以执行块配合goto使用
:d
echo 'aaa'
使用goto执行代码块内容
goto d

用户输入/p使变量值定义为用户输入
set /p a=请输入

引用变量
echo %a%

不显示执行结果 
ping 127.0.0.1  >nul 2>nul
fsutil file createnew D:\system.ini 409600000 >nul 2>nul

```
 
# windows进阶之用户\组

## 用户
```

系统用户
本地用户
  administrator 
  guest
网络用户

查看用户列表
net user

查看用户详细信息
net user Administrator

修改Administrator密码
net user Administrator password

新建账户 /add
net user username password /add 

删除用户 /del
net user username /del

```

## 组

```
列出本地组
net localgroup

创建组 /add
net localgroup  groupname /add

删除组 /del
net localgroup  groupname /del

查看组用户
net localgroup Administrators

添加用户到组 /add
net localgroup Administrators username /add

删除组内用户 /del(administrator 最高管理员权限)
net localgroup Administrators username /del

激活/禁用户 /active:yes/no
net localgroup Administrators username /active:yes
net localgroup Administrators username /active:no


```
# windows远程管理

```
开启远程桌面
我的电脑邮件属性高级系统设置远程允许远程连接到此计算机
非管理员账号要加到组内 
net localgroup Remote Desktop Users  user /add
远程连接
mstsc

远程管理工具
telnet 

开启telnet服务
services.msc打开telnet服务
将用户添加到telnetClients组内

telnet远程连接(不加密)
telnet 127.0.0.1 















```
