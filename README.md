OSCP备考的干货知识~
- [oscp lab vpn不稳定？每次都要输入密码很麻烦？点我~](https://github.com/Jewel591/OSCP-Tips/blob/master/others/%E5%85%B3%E4%BA%8Eopenvpn.md)

# 边界突破
## Web服务
- [PHP突破及反弹shell](https://github.com/Jewel591/OSCP/blob/master/PHP-reverse-shell/README.md)

- [ASP突破及反弹shell](https://github.com/Jewel591/OSCP/blob/master/ASP-reverse-shell/README.md)

## 系统服务
## 暴力破解
- [暴力破解方法汇总](https://github.com/Jewel591/OSCP-Tips/blob/master/Brute-Force.md)

## 反弹shell
- 各种shell的姿势汇总：[https://github.com/swisskyrepo/PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/735b0d2277b39cda75af2855362fd5e8ae50b3db/Methodology%20and%20Resources/Reverse%20Shell%20Cheatsheet.md)

# 提权
## Linux 提权
Linux 信息收集
- https://github.com/rebootuser/LinEnum
- https://github.com/AlessandroZ/BeRoot
- https://github.com/mzet-/linux-exploit-suggester

Linux SUID 提权
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
|  表头   | 表头  | 表头  | 
|  ----  | ---- | ----  | 
| [ash](https://github.com/Jewel591/OSCP-Tips/blob/master/Linux-SUID-PE/ash.md)  | chroot | docker |
| [base32](https://github.com/Jewel591/OSCP-Tips/blob/master/Linux-SUID-PE/base64.md)  | csh | emacs | 
| [base64](https://github.com/Jewel591/OSCP-Tips/blob/master/Linux-SUID-PE/base64.md)  | curl  | gdb | 
| [bash](https://github.com/Jewel591/OSCP/blob/master/Linux-SUID-PE/bash.md)  | cut  | env | 
| [busybox](https://github.com/Jewel591/OSCP-Tips/blob/master/Linux-SUID-PE/busybox.md)  | dash  | eqn | 
| [cp](https://github.com/Jewel591/OSCP/blob/master/Linux-SUID-PE/cp-move.md)  | date  | expand | 
| [cat](https://github.com/Jewel591/OSCP-Tips/blob/master/Linux-SUID-PE/cat.md)  | dd  | expect | 
| [chmod](https://github.com/Jewel591/OSCP-Tips/blob/master/Linux-SUID-PE/chmod.md)  | dialog   | file | 
| [chown](https://github.com/Jewel591/OSCP-Tips/blob/master/Linux-SUID-PE/chown.md)  | diff  | [find](https://github.com/Jewel591/OSCP/blob/master/Linux-SUID-PE/find.md) | 
| [docker](https://github.com/Jewel591/OSCP-Tips/blob/master/Linux-SUID-PE/docker.md)  | dmsetup  | flock | 

---
|  fmt  | jq  | nano  |
|  fold |  | jrunscript  | [nmap](https://github.com/Jewel591/OSCP/blob/master/Linux-SUID-PE/nmap.md)  |
|  gimp  | ksh  | nice |
|  grep | ksshell  | nl  |
|  gtester  | ld.so | node  |
|  hd | [less](https://github.com/Jewel591/OSCP/blob/master/Linux-SUID-PE/less-more.md)  | nohup  |
|  head | logsave  | od |
| hexdump  | look  | openssl  |
|  highlight | lwp-download  |[perl](https://github.com/Jewel591/OSCP/blob/master/Linux-SUID-PE/python-perl-ruby-lua-etc.md) |
|  iconv | lwp-request | pg  |
| ionice  | make | php  |
|  ip | [more](https://github.com/Jewel591/OSCP/blob/master/Linux-SUID-PE/less-more.md)  | pico  |
|  jjs | [mv](https://github.com/Jewel591/OSCP/blob/master/Linux-SUID-PE/cp-move.md)  | [python](https://github.com/Jewel591/OSCP/blob/master/Linux-SUID-PE/python-perl-ruby-lua-etc.md) |

---
|  readelf | setarch  | strings  |
|  restic  | shuf  | sysctl  |
| rlwrap  | soelim  | systemctl |
| rpm  | sort  |tac  |
|  rpmquery |start  | tail  |
| rsync  | stop | taskset  |
|  run-parts | daemon  | tclsh  |
| rvim  | stdbuf  | [tcpdump(未验证)](https://github.com/Jewel591/OSCP/blob/master/Linux-SUID-PE/tcpdump.md) |
| sed  | strace | tee  |
| tftp | uniq  | watch |
|  time | unshare  | wget  |
|  timeout | uudecode |xargs  |
| ul  | uuencode  | xxd |
|  unexpand | [vim/vi](https://github.com/Jewel591/OSCP/blob/master/Linux-SUID-PE/vim.md) | xz  |
|  zsh | zsoelim  | [其他脚本文件](https://github.com/Jewel591/OSCP/blob/master/Linux-SUID-PE/other-script-file.md)  |


## Windows 提权
提权方法：
1. [不带引号的服务路径](https://github.com/Jewel591/OSCP/blob/master/PostExploit/WindowsPE/PathwithoutQuotation.md)
2. [易受攻击的服务](https://github.com/Jewel591/OSCP/blob/master/PostExploit/WindowsPE/Accesschk.md)
3. [Windows AlwaysInstallElevated 策略](https://github.com/Jewel591/OSCP/blob/master/PostExploit/WindowsPE/AlwaysInstallElevated.md)
4. Unattended Installs
5. [内核提权](https://github.com/Jewel591/OSCP/blob/master/PostExploit/WindowsPE/Kernel_Exploit.md)

windows 服务提权工具：
1. [Accesschk.exe](https://github.com/Jewel591/OSCP/blob/master/PostExploit/WindowsPE/Accesschk.md)
2. [BeRoot](https://github.com/AlessandroZ/BeRoot/tree/master/Windows)
3. [winPEAS](https://github.com/carlospolop/privilege-escalation-awesome-scripts-suite/tree/master/winPEAS/winPEASexe/winPEAS/bin/Obfuscated%20Releases)
4. [windows-exploit-suggester](https://github.com/AonCyberLabs/Windows-Exploit-Suggester) > [教程](https://www.notion.so/Windows-60898e79f361472ea1939775d4536eb3)
