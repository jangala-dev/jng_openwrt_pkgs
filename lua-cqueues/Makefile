#
# Copyright (C) 2009-2013 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=lua-cqueues
PKG_VERSION:=rel-20200726
PKG_RELEASE:=1

PKG_SOURCE:=cqueues-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/wahern/cqueues/tar.gz/$(PKG_VERSION)?
PKG_HASH:=9e112edd246da5cfca264314b70325a0b63665cb87a00e45ee3ae4f194000d52

include $(INCLUDE_DIR)/package.mk

define Package/lua-cqueues
  SUBMENU:=Lua
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=Lua CQueues
  URL:=http://25thandclement.com/~william/projects/cqueues.html
  MAINTAINER:=Nathaniel Wesley Filardo <nwfilardo@gmail.com>
  DEPENDS:=+lua +libopenssl +librt +libpthread
endef

define Package/cqueues/description
  Continuation Queues: Embeddable asynchronous networking, threading, and
  notification framework for Lua on Unix.
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

define Package/lua-cqueues/install
	$(INSTALL_DIR) $(1)/usr/lib/lua
	$(MAKE) -C $(PKG_BUILD_DIR)/ \
		lua51path=$(1)/usr/lib/lua lua51cpath=$(1)/usr/lib/lua \
		install5.1
endef

$(eval $(call BuildPackage,lua-cqueues))