# OpenWrt package feed for thingsboard-gateway
thingsboard-gateway for openwrt19.07 or openwrt21.02.

This is an OpenWrt package feed containing community maintained python packages.

To use these packages, add the following line to the feeds.conf in the OpenWrt buildroot:



    src-git thingsboard_gateway git://github.com/zhongweijie95/openwrt-thingsboard-gateway-packages


Update the feed:


    ./scripts/feeds update thingsboard_gateway 


Activate the package:


    ./scripts/feeds install -a -p thingsboard_gateway


The thingsboard-gateway packages should now appear in menuconfig.
