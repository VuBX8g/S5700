#华为s5700交换机恢复出厂设置

#首先通过串口线登陆该交换机
#无需进入sys，直接在现有状态下输入reset saved-configuration 并在接下来的询问中选择"Y"。
#此时配置已经清空，现在进行重启操作。输入reboot，并在接下来的第一个询问中选择“N”，第二个询问中选择“Y”。

#华为交换机 为 ETH 分配管理IP  
#执行命令interface MEth 0/0/1，进入MEth接口视图。
#<HUAWEI> system-view 
#[HUAWEI] interface MEth 0/0/1
#执行命令ip address ip-address { mask | mask-length }，配置MEth接口的IP地址。此处假设设备管理网口的IP地址为10.1.1.1/24。
#[HUAWEI-MEth0/0/1] ip address 10.1.1.1 255.255.255.0
#[HUAWEI-Meth0/0/1]quit
#[HUAWEI]ip route-static 10.1.1.1 255.255.255.0 10.1.1.254
#[HUAWEI] 
