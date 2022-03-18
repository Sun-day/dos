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
 



