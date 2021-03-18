#
# Copyright (C) 2007-2017 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=regex
PKG_VERSION:=2020.11.13
PKG_RELEASE:=2
PKG_LICENSE:=MIT
PKG_CPE_ID:=cpe:/a:palletsproject:regex

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/source/r/regex
PKG_HASH:=83d6b356e116ca119db8e7c6fc2983289d87b27b3fac238cfe5dca529d884562
PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python-package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python-$(PKG_NAME)/Default
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=regex
  URL:=https://pypi.org/project/regex/
endef

define Package/python-$(PKG_NAME)
$(call Package/python-$(PKG_NAME)/Default)
  DEPENDS:=+python
  VARIANT:=python
endef

define Package/python3-$(PKG_NAME)
$(call Package/python-$(PKG_NAME)/Default)
  DEPENDS:=+python3
  VARIANT:=python3
endef

define Package/python-$(PKG_NAME)/description
  This regex implementation is backwards-compatible with the standard ‘re’ module, but offers additional functionality.
endef

define Package/python3-$(PKG_NAME)/description
$(call Package/python-$(PKG_NAME)/description)
.
(Variant for Python3)
endef

$(eval $(call PyPackage,python-$(PKG_NAME)))
$(eval $(call BuildPackage,python-$(PKG_NAME)))
$(eval $(call BuildPackage,python-$(PKG_NAME)-src))

$(eval $(call Py3Package,python3-$(PKG_NAME)))
$(eval $(call BuildPackage,python3-$(PKG_NAME)))
$(eval $(call BuildPackage,python3-$(PKG_NAME)-src))
