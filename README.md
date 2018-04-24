# README

刚开始测试的时候是在Buildroot中进行测试，经过查资料，发现Audit依赖的一些统计信息并没有生成，可能是在选择一些依赖的时候没有选上导致的，后来换成[Ubuntu 16.04](https://github.com/ZengjfOS/UbuntuRootFS)，发现统计信息完善了。

## 参考文档

* [Auditd - Linux 服务器安全审计工具](https://linux.cn/article-4907-1.html)
* [Welcome the Linux Audit Documentation Project](https://github.com/linux-audit/audit-documentation/wiki)
* [CHAPTER 1. SECURITY OVERVIEW](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/6/html/security_guide/chap-security_guide-security_overview#sect-Security_Guide-Introduction_to_Security)

## 内核驱动支持设置

* [Linux audit安全审计工具](http://www.cnblogs.com/zengjfgit/p/8921380.html)

## Ubuntu Install Audit

* `sudo apt-get install auditd audispd-plugins`
* 进程查看：
  ```
  root@zengjf:/etc/audit# ps aux | grep audit
  root       108  0.0  0.0      0     0 ?        S    16:28   0:00 [kauditd]
  root       185  0.0  0.1  11788  1324 ?        S<sl 16:28   0:00 /sbin/auditd -n
  root       500  0.0  0.0   3732   544 ttymxc0  S+   16:43   0:00 grep --color=auto audit
  root@zengjf:/etc/audit#
  ```

## Audit分析文档

* [0001_Security_Audit_Base.md](./docs/0001_Security_Audit_Base.md)
