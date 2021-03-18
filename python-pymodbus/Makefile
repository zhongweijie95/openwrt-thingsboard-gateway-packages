#
# Copyright (C) 2007-2017 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=pymodbus
PKG_VERSION:=2.4.0
PKG_RELEASE:=2
PKG_LICENSE:=MIT
PKG_CPE_ID:=cpe:/a:palletsproject:pymodbus

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/source/p/pymodbus
PKG_HASH:=24ff600245b7cc9f4e299d7099eda5f35d000707bec3429f7bd6690637c22cd5
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
  URL:=https://github.com/riptideio/pymodbus
  DEPENDS:=+python3 +python3-pyserial +python3-six
  VARIANT:=python3
endef

define Package/python3-$(PKG_NAME)/description
  Pymodbus aims to be a fully implemented modbus protocol stack implemented using twisted/asyncio/tornado. Its orignal goal was to allow simulation of thousands of modbus devices on a single machine for monitoring software testing.
endef

$(eval $(call Py3Package,python3-$(PKG_NAME)))
$(eval $(call BuildPackage,python3-$(PKG_NAME)))
$(eval $(call BuildPackage,python3-$(PKG_NAME)-src))
