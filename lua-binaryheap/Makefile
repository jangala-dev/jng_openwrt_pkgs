#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=lua-binaryheap
PKG_VERSION:=version_0v4
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/Tieske/binaryheap.lua/tar.gz/refs/tags/$(PKG_VERSION)?
PKG_HASH:=10b1b6c6f2d22560f512f9896a6672ec5ae0eea1390ff8e662be1d5d9625b438
PKG_BUILD_DIR:=$(BUILD_DIR)/binaryheap.lua-$(PKG_VERSION)

PKG_MAINTAINER:=Rich Thanki <rich@janga.la>
PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE

PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/lua-binaryheap
	SUBMENU:=Lua
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=lua-binaryheap
	URL:=https://github.com/Tieske/binaryheap.lua
	DEPENDS:=+lua
	PKGARCH:=all
endef

define Package/lua-binaryheap/description
	Binary heap implementation in lua.
endef

define Build/Configure
endef

define Build/Compile
endef

define Build/Install
endef

define Package/lua-binaryheap/install
	$(INSTALL_DIR) $(1)/usr/lib/lua

	$(CP) $(PKG_BUILD_DIR)/src/* $(1)/usr/lib/lua/
endef

$(eval $(call BuildPackage,lua-binaryheap))