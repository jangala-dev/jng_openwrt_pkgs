include $(TOPDIR)/rules.mk

PKG_NAME:=lua-lumen
PKG_VERSION:=2.0
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/xopxe/lumen.git
PKG_SOURCE_DATE:=2021-07-09
PKG_SOURCE_VERSION:=001a2e86088d147af30009953ba5fcc03128d383

PKG_MAINTAINER:=Rich <rich@janga.la>
PKG_LICENSE:=MIT

include $(INCLUDE_DIR)/package.mk

define Package/lua-lumen
	SUBMENU:=Lua
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=Lumen
	DEPENDS:=+lua
	PKGARCH:=all
endef

define Package/lua-lumen/description
	Lumen is a very simple environment for coroutine based multitasking.
endef

define Build/Configure
endef

define Build/Compile
endef

define Build/Install
endef

define Package/lua-lumen/install
	$(INSTALL_DIR) $(1)/usr/lib/lua
	$(INSTALL_DIR) $(1)/usr/lib/lua/lumen
	$(INSTALL_DIR) $(1)/usr/lib/lua/lumen/lib
	$(INSTALL_DIR) $(1)/usr/lib/lua/lumen/tasks
	$(INSTALL_DIR) $(1)/usr/lib/lua/lumen/tasks/http-server
	$(INSTALL_DIR) $(1)/usr/lib/lua/lumen/tasks/http-server/websocket
	$(INSTALL_DIR) $(1)/usr/lib/lua/lumen/tasks/http-server/www

	$(CP) $(PKG_BUILD_DIR)/*.lua 								$(1)/usr/lib/lua/lumen/
	$(CP) $(PKG_BUILD_DIR)/lib/*.lua 							$(1)/usr/lib/lua/lumen/lib/
	$(CP) $(PKG_BUILD_DIR)/tasks/*.lua 							$(1)/usr/lib/lua/lumen/tasks/
	$(CP) $(PKG_BUILD_DIR)/tasks/http-server/*.lua 				$(1)/usr/lib/lua/lumen/tasks/http-server/
	$(CP) $(PKG_BUILD_DIR)/tasks/http-server/websocket/*.lua	$(1)/usr/lib/lua/lumen/tasks/http-server/websocket/
	$(CP) $(PKG_BUILD_DIR)/tasks/http-server/www/* 				$(1)/usr/lib/lua/lumen/tasks/http-server/www/
endef

$(eval $(call BuildPackage,lua-lumen))