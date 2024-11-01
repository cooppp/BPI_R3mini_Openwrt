<img src="https://openwrt.org/_media/logo.png" alt="logo" width="274" height="84" align="right">

# OpenWrt项目

这个项目fork自[OpenWrt](https://github.com/openwrt/openwrt)

默认登录地址: http://172.16.0.1, 用户名: __root__, 密码: 无.

## 如何编译自己需要的 OpenWrt 固件

### 快速开始

1. 执行命令 `git clone -b <branch> --single-branch https://github.com/SandroDickens/openwrt.git` 下载源码.
2. 执行命令 `cd openwrt` 进入源码目录.
3. 执行命令 `./scripts/feeds update -a` 获取feeds.conf / feeds.conf.default中定义的最新的包.
4. 执行命令 `./scripts/feeds install -a` to install symlinks for all obtained packages into package/feeds/
5. 执行命令 `make menuconfig` 选择你需要的toolchain, target system和firmware包生成配置文件.
6. 执行命令 `make download -j$(nproc) V=sc` 下载源码、交叉编译工具链、Linux内核等(需要能访问国际互联网, 此过程可能会有部分文件下载失败, 为保守起见最好执行2遍).
7. 执行命令 `make -j$(nproc) V=sc` 编译固件.

### BPI编译

1 下载源码 git clone --depth=1 -b stable-v23 https://github.com/cooppp/BPI_R3mini_Openwrt.git openwrt

2 下载packages 进入源码目录

cd openwrt.

/prebuild.sh

3 编译

模板配置文件

cp config-bpi-r3-mini .config

自定义插件

make menuconfig

执行脚本

./build.sh

输出路径:bin/targets/mediatek/filogic

或者你可以直接下载神秘人士编译好的[固件](https://github.com/SandroDickens/openwrt/releases/tag/v23.05.2/)
4. 测速

经测试, 无论是否开启硬件加速, 都能跑满2.5G

## License

OpenWrt is licensed under GPL-2.0
