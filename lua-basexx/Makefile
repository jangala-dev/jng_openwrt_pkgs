#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=lua-basexx
PKG_VERSION:=0.4.1
PKG_RELEASE:=1

PKG_SOURCE:=basexx-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/aiq/basexx/tar.gz/refs/tags/v$(PKG_VERSION)?
PKG_HASH:=ff62b00446df1181a9cd20ba970c3c8493165d262142e10d069ee3de6337dfe6
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

PKG_MAINTAINER:=Rich Thanki <rich@janga.la>
PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE

PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/lua-basexx
  SUBMENU:=Lua
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=lua-basexx
  URL:=https://github.com/aiq/basexx
  DEPENDS:=+lua
  PKGARCH:=all
endef

define Package/lua-basexx/description
  A Lua library for base2, base16, base32, base64, base85 decoding and encoding of data strings.
endef

define Build/Configure
endef

define Build/Compile
endef

define Build/Install
endef

# add make variable overrides here
MAKE_FLAGS +=

define Package/lua-basexx/install
	$(INSTALL_DIR) $(1)/usr/lib/lua
	$(INSTALL_DIR) $(1)/usr/lib/lua/basexx
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/lib/basexx.lua $(1)/usr/lib/lua/basexx
endef

$(eval $(call BuildPackage,lua-basexx))