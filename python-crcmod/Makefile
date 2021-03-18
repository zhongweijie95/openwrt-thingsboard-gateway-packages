#
# Copyright (C) 2007-2017 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=crcmod
PKG_VERSION:=1.7
PKG_RELEASE:=2
PKG_LICENSE:=MIT
PKG_CPE_ID:=cpe:/a:palletsproject:crcmod

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://nchc.dl.sourceforge.net/project/crcmod/crcmod/$(PKG_NAME)-$(PKG_VERSION)
PKG_HASH:=dc7051a0db5f2bd48665a990d3ec1cc305a466a77358ca4492826f41f283601e
PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk
include $(TOPDIR)/feeds/packages/lang/python/pypi.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python3-$(PKG_NAME)
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=pymodbus
  URL:=https://sourceforge.net/projects/crcmod/files/crcmod/
  DEPENDS:=+python3
  VARIANT:=python3
endef

define Package/python3-$(PKG_NAME)/description
  Python module for creating functions computing the Cyclic Redundancy Check (CRC). Any generating polynomial producing 8, 16, 24, 32, or 64 bit CRCs is allowed. Generated functions can be used in Python or C/C++ source code can be generated.
endef

$(eval $(call Py3Package,python3-$(PKG_NAME)))
$(eval $(call BuildPackage,python3-$(PKG_NAME)))
$(eval $(call BuildPackage,python3-$(PKG_NAME)-src))
