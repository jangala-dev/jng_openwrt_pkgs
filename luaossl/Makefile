#
# Copyright (C) 2009-2013 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=luaossl
PKG_VERSION:=rel-20200709
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/wahern/luaossl/tar.gz/$(PKG_VERSION)?
PKG_HASH:=f3054e1ce26ca65ecaa7dcf193ea97d6a06933e4aa516779ebb89a6727d8a28f

include $(INCLUDE_DIR)/package.mk

define Package/luaossl
  SUBMENU:=Lua
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=luaossl
  URL:=http://25thandclement.com/~william/projects/luaossl.html
  MAINTAINER:=Rich <rich@janga.la>
  DEPENDS:=+lua +libopenssl +libpthread
endef

define Package/luaossl/description
  luaossl is a comprehensive binding to OpenSSL for Lua 5.1, 5.2, and later.
endef

define Build/Configure
endef

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR)/ \
		LUA_APIS="5.1" \
		ALL_LDFLAGS="$(TARGET_LDFLAGS)" \
		CC="$(TARGET_CC) $(TARGET_CFLAGS) $(TARGET_CPPFLAGS) -fPIC -std=gnu99" \
		LD="$(TARGET_CROSS)ld -shared" \
		all5.1
endef

define Package/luaossl/install
	$(INSTALL_DIR) $(1)/usr/lib/lua
	$(MAKE) -C $(PKG_BUILD_DIR)/ \
		lua51path=$(1)/usr/lib/lua lua51cpath=$(1)/usr/lib/lua \
		install5.1
endef

$(eval $(call BuildPackage,luaossl))
