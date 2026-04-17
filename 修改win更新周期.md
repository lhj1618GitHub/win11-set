暂停 Windows 自动更新的方法：
1. 开始 - 运行，输入 `regedit` ，回车自动打开注册表
2. 定位到 `\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\WindowsUpdate\UX\Settings`
3. 在右侧右键菜单选择「新建DWORD（32位）值(D)」，重命名为 `FlightSettingsMaxPauseDays`
4. 双击「FlightSettingsMaxPauseDays」，修改基数为「十进制」，修改为需要的天数 `9999`
