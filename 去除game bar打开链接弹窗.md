运行下面的命令

```
reg add "HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\GameDVR" /v "AppCaptureEnabled" /t "REG_DWORD" /d "0" /f
reg add "HKCU\System\GameConfigStore" /v "GameDVR_Enabled" /t "REG_DWORD" /d "0" /f
```

参考说明：[https://bbs.pcbeta.com/forum.php?mod=redirect&goto=findpost&ptid=1972471&pid=54083714](https://bbs.pcbeta.com/forum.php?mod=redirect&goto=findpost&ptid=1972471&pid=54083714)
