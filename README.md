# OpenWrt package feed for thingsboard-gateway
thingsboard-gateway for openwrt19.07.

This is an OpenWrt package feed containing community maintained python packages.

To use these packages, add the following line to the feeds.conf in the OpenWrt buildroot:



    src-git thingsboard-gateway git://github.com/zhongweijie95/thingsboard-gateway.git


Update the feed:


    ./scripts/feeds update thingsboard-gateway 


Activate the package:


    ./scripts/feeds install -a -p thingsboard-gateway


The thingsboard-gateway packages should now appear in menuconfig.
