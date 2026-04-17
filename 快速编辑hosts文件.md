效果图

<img width="240" height="138" alt="{F6F0A44E-84DF-47EF-8D52-13813A2962D2}" src="https://github.com/user-attachments/assets/fd52ca0a-920f-4574-8a6a-7099a525fa24" />

复制下面的内容保存为.bat文件，直接运行可快速打开hosts文件/刷新DNS缓存

```
@ECHO OFF
mode con cols=30 lines=10
TITLE 修改hosts文件
color 2F
%Windir%\System32\FLTMC.exe >nul 2>&1 || (
    ECHO CreateObject^("Shell.Application"^).ShellExecute "%~f0", "%PAR1st%", "", "runas", 1 > "%TEMP%\AdminRun.vbs"
    ECHO CreateObject^("Scripting.filesystemobject"^).DeleteFile ^(WScript.ScriptFullName^) >> "%TEMP%\AdminRun.vbs"
    %Windir%\System32\CSCRIPT.exe //Nologo "%TEMP%\AdminRun.vbs"
    Exit /b
)
ECHO 　　　hosts已打开
notepad "%SystemRoot%\system32\drivers\etc\hosts"
echo.
:Menu
Cls
@ echo.
@ echo.	菜 单 选 项
@ echo.
@ echo.	1.打开hosts文件
@ echo.
@ echo.	2.刷新DNS缓存
@ echo.
@ echo.	3.退出
@ echo.
set /p xj= 输入数字，然后按回车：
if /i "%xj%"=="1" Goto Open
if /i "%xj%"=="2" Goto DNS
if /i "%xj%"=="3" Goto Exit
@ echo.
echo      选择无效，请重新输入
ping -n 2 127.1>nul
goto menu

:Open
@ echo.
ECHO 　　　hosts已打开
notepad "%SystemRoot%\system32\drivers\etc\hosts"
goto menu

:DNS
@ echo.
ipconfig /flushdns
echo.
cls
@ echo.
echo 		DNS已刷新
pause 
@ echo.
goto menu

```


