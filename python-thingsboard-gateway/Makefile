#
# Copyright (C) 2007-2017 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=thingsboard-gateway
PKG_VERSION:=2.5.5.2
PKG_RELEASE:=2
PKG_LICENSE:=MIT
PKG_CPE_ID:=cpe:/a:palletsproject:thingsboard-gateway

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/thingsboard/thingsboard-gateway/tar.gz/$(PKG_VERSION)?
PKG_HASH:=e871fa9559bb8742683e6d5aa1ea255b026822b313a46ee802fbabb343d5abf1
PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-$(PKG_NAME)-$(PKG_VERSION)

include $(TOPDIR)/feeds/packages/lang/python/pypi.mk
include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python3-$(PKG_NAME)
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=Thingsboard gateway
  URL:=https://github.com/thingsboard/thingsboard-gateway
  DEPENDS:=+python3 +python3-dev +python3-paho-mqtt +python3-simplejson \
	   +python3-pip +python3-requests +python3-pyserial \
	   +python3-yaml +python3-regex +python3-jsonpath-rw \
	   +python3-bacpypes +python3-pymodbus +python3-bluepy
  VARIANT:=python3
endef

define Package/python3-$(PKG_NAME)/description
  Thingsboard gateway for Python3
endef

define Py3Package/python3-$(PKG_NAME)/install
	if [ -d $(PKG_INSTALL_DIR)/usr/bin/ ]; then \
		$(INSTALL_DIR) $(1)/usr/bin/ ; \
		$(CP) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin/ ; \
	fi

	$(INSTALL_DIR) $(1)/etc
	$(CP) ./files/etc/* $(1)/etc

	$(INSTALL_DIR) $(1)/tmp
	$(CP) ./files/var/* $(1)/tmp
endef

$(eval $(call Py3Package,python3-$(PKG_NAME)))
$(eval $(call BuildPackage,python3-$(PKG_NAME)))
$(eval $(call BuildPackage,python3-$(PKG_NAME)-src))
