#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=cffi-lua
PKG_VERSION:=0.2.3
PKG_RELEASE:=$(AUTORELEASE)

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/q66/cffi-lua/tar.gz/refs/tags/v$(PKG_VERSION)
PKG_HASH:=1d2577a62a843e5e6db35af1b58300d279b4df58eccef5e823441501f960d388

PKG_MAINTAINER:=Rich Thanki <rich@janga.la>
PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=COPYING.md

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/meson.mk

define Package/cffi-lua
  TITLE:=cffi-lua
  DEPENDS:=+libffi +lua +luac +liblua
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Lua
  URL:=https://github.com/q66/cffi-lua
endef

define Package/cffi-lua/description
	A portable C FFI for Lua 5.1+.
endef

MESON_ARGS += \
	-Dlua_version=5.1

define Package/cffi-lua/install
	$(INSTALL_DIR) $(1)/usr/lib/lua
	$(CP) $(PKG_INSTALL_DIR)/usr/local/lib/lua/5.1/cffi.so $(1)/usr/lib/lua
endef

$(eval $(call BuildPackage,cffi-lua))
