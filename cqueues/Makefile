#
# Copyright (C) 2009-2013 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=cqueues
PKG_VERSION:=rel-20190813
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/wahern/$(PKG_NAME)/archive
PKG_HASH:=24f1aa69b539e6796445c2228f921744ad64f9336498c7537bee97719d914804

include $(INCLUDE_DIR)/package.mk

define Package/lua-cqueues
  SUBMENU:=Lua
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=Lua-CQueues
  URL:=http://25thandclement.com/~william/projects/cqueues.html
  MAINTAINER:=Nathaniel Wesley Filardo <nwfilardo@gmail.com>
  DEPENDS:=+lua +libopenssl +librt +libpthread
endef

define Package/lua-cqueues/description
  Continuation Queues: Embeddable asynchronous networking, threading, and
  notification framework for Lua on Unix.
endef

define Build/Configure
endef

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR)/ \
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
