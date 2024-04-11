### 1、PowerShell 

```
1.查看包名：Get-AppxPackage | Select Name, PackageFullName
2.卸载系统自带软件：
  人脉：get-appxpackage *Microsoft.People* | remove-appxpackage
  相机：get-appxpackage *Microsoft.WindowsCamera* | remove-appxpackage
  照片：get-appxpackage *Microsoft.Windows.Photos* | remove-appxpackage
  应用商店：get-AppxPackage *windowsstore* | Remove-AppxPackage
  手机链接：Get-AppxPackage *Microsoft.YourPhone* | Remove-AppxPackage
  获取帮助：get-appxpackage *Microsoft.GetHelp* | remove-appxpackage
  闹钟与时钟：get-appxpackage *Microsoft.WindowsAlarms* | remove-appxpackage
```

### 2、Regedit

```
1.删除3D对象文件夹
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace\{0DB7E03F-FC29-4DC6-9020-FF41B59E513A}
2.删除设备图标
HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\MyComputer\NameSpace
3.添加或删除程序失败
HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall
4.删除右键菜单
HKEY_CLASSES_ROOT     ---搜索ShellNew，将想要删除的删掉就行
5.去除已卸载程序在"选择在任务栏上显示哪些图标" 这个选项下的显示
HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\TrayNotify
或者HKEY_CLASSES_ROOT\Local Settings\Software\Microsoft\Windows\CurrentVersion\TrayNotify
删除IconStreams和PastIconsStream，任务管理器结束explorer.exe，再点击文件-新建任务输入explorer，回车
```

### 3、Reg

```
1.alt+tab失效
REGEDIT4[HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer]"AltTabSettings"=dword:00000001
```
