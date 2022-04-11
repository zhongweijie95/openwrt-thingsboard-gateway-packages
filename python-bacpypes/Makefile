#
# Copyright (C) 2007-2017 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=bacpypes
PKG_VERSION:=0.18.1
PKG_RELEASE:=2
PKG_LICENSE:=MIT
PKG_CPE_ID:=cpe:/a:palletsproject:bacpypes
PKG_MAINTAINER:=weijie-zhong <zhongweijie95@vip.qq.com>

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/JoelBender/bacpypes/tar.gz/$(PKG_VERSION)?
PKG_HASH:=d55f0f92870e4717b54b3c5679482affe5a00ca3b6ad1b29d16e5c56cc3fda94
PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python3-$(PKG_NAME)
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=BACpypes
  URL:=https://github.com/JoelBender/bacpypes
  DEPENDS:=+python3
  VARIANT:=python3
endef

define Package/python3-$(PKG_NAME)/description
  BACpypes provides a BACnet application layer and network layer written in Python for daemons, scripting, and graphical interfaces.
endef

$(eval $(call Py3Package,python3-$(PKG_NAME)))
$(eval $(call BuildPackage,python3-$(PKG_NAME)))
$(eval $(call BuildPackage,python3-$(PKG_NAME)-src))
