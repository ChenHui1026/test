# test
#1、删除.repo文件和删除其他客户配置的代码相关以及apk
#2、给客户服务器下的opt文件
#3、修改.bashrc文件内容并添加 vi ~/.bashrc或者sudo vi etc/bash.bashrc文件的内容为：
#rm-none-linux-gnueabi!/bin/sh
SET_PATH=$( echo "$PATH" | grep gnueabi)
if [  "$SET_PATH" = "" ]; then
#ARC_PREFIX=/opt/gnutools/arc2.2-p4
ARM_PREFIX=/opt/CodeSourcery/Sourcery_G++_Lite
PATH=$PATH:${ARM_PREFIX}/bin:${ARM_PREFIX}/arm-none-eabi/bin:${ARM_PREFIX}/arm-none-linux-gnueabi/bin:/opt/gcc-linaro-arm-linux-gnueabihf/bin
fi
#!/bin/sh
SET_PATH=$( echo "$PATH" | grep elf32)
if [  "$SET_PATH" = "" ]; then
#ARC_PREFIX=/opt/gnutools/arc2.2-p4
ARC_PREFIX=/opt/gnutools/arc2.3-p0
PATH=$PATH:${ARC_PREFIX}/elf32-4.2.1/bin:${ARC_PREFIX}/uclibc-4.2.1/bin:
fi
#!/bin/sh
SET_PATH=$( echo "$PATH" | grep elf32-em4)
if [  "$SET_PATH" = "" ]; then
ARC_PREFIX=/opt/gnutools/arc-4.8-amlogic-20130904-r2
PATH=$PATH:${ARC_PREFIX}/bin
fi

#for amlogic s905
PATH=$PATH:/opt/gcc-linaro-aarch64-linux-gnu-4.9-2014.09_linux/bin:/opt/gcc-linaro-aarch64-none-elf-4.8-2013.11_linux/bin

PATH=$PATH:/opt/riscv-none-gcc/7.2.0-4-20180606-1631/bin
#4、使修改的环境编译成功：source etc/bash.bashrc
