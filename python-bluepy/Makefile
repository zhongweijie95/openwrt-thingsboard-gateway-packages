#
# Copyright (C) 2007-2017 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=bluepy
PKG_VERSION:=1.3.0
PKG_RELEASE:=2
PKG_LICENSE:=MIT
PKG_CPE_ID:=cpe:/a:palletsproject:bluepy
PKG_MAINTAINER:=weijie-zhong <zhongweijie95@vip.qq.com>

PKG_SOURCE:=$(PKG_NAME)-v-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/IanHarvey/bluepy/tar.gz/v/$(PKG_VERSION)?
PKG_HASH:=878e68e6d0f2823a5ebc5763e97ed887cc599120a5cc0bac577b7d655db6cd3e
PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk
include $(TOPDIR)/feeds/packages/lang/python/pypi.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python3-$(PKG_NAME)
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=Python interface to Bluetooth LE on Linux
  URL:=https://github.com/IanHarvey/bluepy
  DEPENDS:=+python3 +glib2
  VARIANT:=python3
endef

define Package/python3-$(PKG_NAME)/description
  Python interface to Bluetooth LE on Linux
endef

$(eval $(call Py3Package,python3-$(PKG_NAME)))
$(eval $(call BuildPackage,python3-$(PKG_NAME)))
$(eval $(call BuildPackage,python3-$(PKG_NAME)-src))
