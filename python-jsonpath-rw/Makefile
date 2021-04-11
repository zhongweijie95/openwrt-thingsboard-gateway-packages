#
# Copyright (C) 2007-2017 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=jsonpath-rw
PKG_VERSION:=1.4.0
PKG_RELEASE:=2
PKG_LICENSE:=MIT
PKG_CPE_ID:=cpe:/a:palletsproject:jsonpath-rw
PKG_MAINTAINER:=weijie-zhong <zhongweijie95@vip.qq.com>

PKG_SOURCE:=python-$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/kennknowles/python-jsonpath-rw/tar.gz/$(PKG_VERSION)?
PKG_HASH:=0aac3458f78b115e661a51610b631c46f27c8b6a4446e4dafb9a13b5ddb5d5e7
PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python-package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python-$(PKG_NAME)/Default
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=jsonpath-rw
  URL:=https://github.com/kennknowles/python-jsonpath-rw
endef

define Package/python-$(PKG_NAME)
$(call Package/python-$(PKG_NAME)/Default)
  DEPENDS:=+python +python-ply +python-decorator \
	   +python-six
  VARIANT:=python
endef

define Package/python3-$(PKG_NAME)
$(call Package/python-$(PKG_NAME)/Default)
  DEPENDS:=+python3 +python3-ply +python3-decorator \
	   +python3-six
  VARIANT:=python3
endef

define Package/python-$(PKG_NAME)/description
  This library provides a robust and significantly extended implementation of JSONPath for Python. It is tested with Python 2.6, 2.7, 3.2, 3.3. (On travis-ci there is a segfault when running the tests with pypy; I don’t think the problem lies with this library).

This library differs from other JSONPath implementations in that it is a full language implementation, meaning the JSONPath expressions are first class objects, easy to analyze, transform, parse, print, and extend. (You can also execute them :-)
endef


define Package/python3-$(PKG_NAME)/description
$(call Package/python-$(PKG_NAME)/description)
.
(Variant for Python3)
endef

#$(eval $(call PyPackage,python-$(PKG_NAME)))
#$(eval $(call BuildPackage,python-$(PKG_NAME)))
#$$(eval $(call BuildPackage,python-$(PKG_NAME)-src))

$(eval $(call Py3Package,python3-$(PKG_NAME)))
$(eval $(call BuildPackage,python3-$(PKG_NAME)))
$(eval $(call BuildPackage,python3-$(PKG_NAME)-src))
