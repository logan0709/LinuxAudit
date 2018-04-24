# Security Audit Base

## Audit工具说明

安装完毕后将自动安装以下auditd和相关的工具：

* `auditctl` : 即时控制审计守护进程的行为的工具，比如如添加规则等等。
* `/etc/audit/audit.rules` : 记录审计规则的文件。
* `aureport` : 查看和生成审计报告的工具。
* `ausearch` : 查找审计事件的工具
* `auditspd` : 转发事件通知给其他应用程序，而不是写入到审计日志文件中。
* `autrace` : 一个用于跟踪进程的命令。
* `/etc/audit/auditd.conf` : auditd工具的配置文件。

## 使用方法

* 文件审计：`sudo auditctl -w /etc/passwd -p rwxa`
* 目录伸进：`sudo auditctl -w /production/`
* 审计规则列表：`auditctl -l`
* 查看文件审计结果：`sudo ausearch -f /etc/passwd`
* aureport查看审计报告：
  ```
  root@zengjf:~# aureport
  
  Summary Report
  ======================
  Range of time in logs: 02/11/2016 16:28:02.138 - 02/11/2016 17:48:39.060
  Selected time for report: 02/11/2016 16:28:02 - 02/11/2016 17:48:39.060
  Number of changes in configuration: 0
  Number of changes to accounts, groups, or roles: 2
  Number of logins: 2
  Number of failed logins: 3
  Number of authentications: 11
  Number of failed authentications: 15
  Number of users: 2
  Number of terminals: 6
  Number of host names: 2
  Number of executables: 8
  Number of commands: 2
  Number of files: 0
  Number of AVC's: 0
  Number of MAC events: 0
  Number of failed syscalls: 0
  Number of anomaly events: 0
  Number of responses to anomaly events: 0
  Number of crypto events: 0
  Number of integrity events: 0
  Number of virt events: 0
  Number of keys: 0
  Number of process IDs: 30
  Number of events: 173
  
  root@zengjf:~#
  ```
