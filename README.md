### 自用AX6一键编译脚本
- IMM官方项目没有NSS加速，要编译没有nss加速的是首选！

- LEDE显示有nss，但是测试WIFI有问题，内网中上传速度特别慢。

- 以下两个项目是支持大分区，而且带NSS加速！

1、LiBwrt：https://github.com/LiBwrt-op/openwrt-6.x.git build-AX6-IPQ脚本【该项目近期发现nss加速启动不了】
2、VIKINGYFY： https://github.com/VIKINGYFY/immortalwrt.git build-AX6-NSS脚本【该项目nss加速满血，500m跑满cpu占用个位数!】

- 注意：

开机后执行：

uci set network.@device[0].packet_steering=0
uci set network.@device[0].flow_offloading=0
uci set network.@device[0].flow_offloading_hw=0
uci commit network

nss加速默认是开启的，不要去防火墙里打开系统的硬件或软件卸载加速，会有不可预测的冲突！
测试只要跑大流量cpu占用很低或没有就是NSS加速在起作用了！  
在线ipk软件源：  
src/gz immortalwrt_core https://downloads.immortalwrt.org/releases/24.10-SNAPSHOT/targets/qualcommax/ipq807x/packages/  
src/gz immortalwrt_base https://downloads.immortalwrt.org/releases/24.10-SNAPSHOT/packages/aarch64_cortex-a53/base  
src/gz immortalwrt_luci https://downloads.immortalwrt.org/releases/24.10-SNAPSHOT/packages/aarch64_cortex-a53/luci  
src/gz immortalwrt_packages https://downloads.immortalwrt.org/releases/24.10-SNAPSHOT/packages/aarch64_cortex-a53/packages  
src/gz immortalwrt_routing https://downloads.immortalwrt.org/releases/24.10-SNAPSHOT/packages/aarch64_cortex-a53/routing  
src/gz immortalwrt_telephony https://downloads.immortalwrt.org/releases/24.10-SNAPSHOT/packages/aarch64_cortex-a53/telephony  

- 高通OPENWRT其他大佬项目：

下面的这些项目带nss加速，但是只支持官方的分区！

https://github.com/JiaY-shi/openwrt.git

https://github.com/qosmio/openwrt-ipq.git

https://github.com/King-Of-Knights/openwrt-6.x.git


![微信截图_20241116071934](https://github.com/user-attachments/assets/617a2d49-0f51-485c-a20a-b25cde5a8e82)
![微信截图_20241116071804](https://github.com/user-attachments/assets/502012e5-83d0-4e4b-be8b-a53c1edd0f8b)
