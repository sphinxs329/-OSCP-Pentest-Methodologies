# OSCP
some tips for oscp
# PHP-reverse-shell
[php-reverse-shell-README.md](https://github.com/Jewel591/OSCP/blob/master/PHP-reverse-shell/README.md)


# Linux PE
- https://github.com/rebootuser/LinEnum
- https://github.com/AlessandroZ/BeRoot
- https://github.com/mzet-/linux-exploit-suggester
## SUID 提权
suid 辅助信息收集脚本：
[linux-pe-suid.sh](https://github.com/Jewel591/OSCP/blob/master/Linux-SUID-PE/linux-pe-suid.sh)

原理:
```
#以下命令将尝试查找具有root权限的SUID的文件，不同系统适用于不同的命令，请逐个尝试
find / -perm -u=s -type f 2>/dev/null
find / -user root -perm -4000-print2>/dev/null
find / -user root -perm -4000-exec ls -ldb {} \;
```
已知的可用来提权的linux可行性的文件列表如下：
- [nmap](https://github.com/Jewel591/OSCP/blob/master/Linux-SUID-PE/nmap.md)
- vim
- find
- bash
- more
- less
- nano
- cp

# Referer
- https://github.com/swisskyrepo/PayloadsAllTheThings
