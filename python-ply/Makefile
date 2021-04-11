#
# Copyright (C) 2007-2017 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=ply
PKG_VERSION:=3.11
PKG_RELEASE:=2
PKG_LICENSE:=MIT
PKG_CPE_ID:=cpe:/a:palletsproject:ply
PKG_MAINTAINER:=weijie-zhong <zhongweijie95@vip.qq.com>

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/source/p/ply
PKG_HASH:=00c7c1aaa88358b9c765b6d3000c6eec0ba42abca5351b095321aef446081da3
PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk
include $(TOPDIR)/feeds/packages/lang/python/pypi.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python3-$(PKG_NAME)
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=regex
  URL:=https://pypi.org/project/ply/#description
  DEPENDS:=+python3 +python3-pip
  VARIANT:=python3
endef

define Package/python3-$(PKG_NAME)/description
  PLY is yet another implementation of lex and yacc for Python. Some notable features include the fact that its implemented entirely in Python and it uses LALR(1) parsing which is efficient and well suited for larger grammars.

PLY provides most of the standard lex/yacc features including support for empty productions, precedence rules, error recovery, and support for ambiguous grammars.

PLY is extremely easy to use and provides very extensive error checking. It is compatible with both Python 2 and Python 3.
endef

$(eval $(call Py3Package,python3-$(PKG_NAME)))
$(eval $(call BuildPackage,python3-$(PKG_NAME)))
$(eval $(call BuildPackage,python3-$(PKG_NAME)-src))
