### 方法一：通过编辑 rc.local 实现开机启动

在 /etc/rc.local 的 “exit 0” 前添加要执行的命令，即可实现开机启动。

### 方法二：通过添加开机启动服务实现开机启动

创建要执行的脚本，并将脚本复制或者软连接到 /etc/init.d 目录下。

#### 添加服务

```
cd /etc/init.d
sudo update-rc.d 脚本文件名 defaults XX
```
* XX 为数字，表示启动顺序，一般来说设为99即可

#### 移除服务
```
cd /etc/init.d
sudo update-rc.d -f 脚本文件名 remove
```
