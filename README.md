# 使用教程

1. 在u-boot目录下执行脚本make（./make.sh）
2. 配置并make qemu（./configure --target-list=riscv64-linux-user,riscv64-softmmu 之后 make)
3. 修改qemu目录/etc下的qemu-ifup/ifdown，将IFNAME=enp0s3中等号后的部分替换为使用机器ifconfig显示的网卡设备名
4. 修改脚本e1000.sh，sudo后是qemu路径，-kernel后跟编译好的u-boot文件路径，file后是image文件，script和downscript分别是两个脚本。
5. 执行e1000.sh启动QEMU，接入GDB可调试
6. 退出GDB后需执行resume.sh恢复网络通路
7. wireshark抓tap0 interface的数据包即可监测相关通讯

