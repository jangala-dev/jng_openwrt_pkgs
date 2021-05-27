include $(TOPDIR)/rules.mk

PKG_NAME:=lua-lumen
PKG_VERSION:=2.0
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/xopxe/lumen.git
PKG_SOURCE_DATE:=2021-05-02
PKG_SOURCE_VERSION:=090b2ad140655d095e376d39dc0308eea1900361
PKG_MIRROR_HASH:=4490d3ad831d64c8b5f31998189dd7cd62317a352f6082572c5606b660098130

# PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

PKG_MAINTAINER:=Jorge <xxopxe@gmail.com>

include $(INCLUDE_DIR)/package.mk

define Package/lua-lumen
	SECTION:=core
	CATEGORY:=JNG
	TITLE:=Lumen
	DEPENDS:=+lua
endef

define Package/lua-lumen/description
	Lumen is a very simple environment for coroutine based multitasking.
endef

define Build/Compile
	echo "Nothing to compile, pure lua package"
endef

define Package/lua-lumen/install
	$(INSTALL_DIR) $(1)/usr/lib/lua/
	$(INSTALL_DIR) $(1)/usr/lib/lua/lumen
	$(INSTALL_DIR) $(1)/usr/lib/lua/lumen/lib
	$(INSTALL_DIR) $(1)/usr/lib/lua/lumen/tasks
	$(INSTALL_DIR) $(1)/usr/lib/lua/lumen/tasks/http-server
	$(INSTALL_DIR) $(1)/usr/lib/lua/lumen/tasks/http-server/websocket
	$(INSTALL_DIR) $(1)/usr/lib/lua/lumen/tasks/http-server/www

	$(CP) $(PKG_BUILD_DIR)/*.lua 								$(1)/usr/lib/lua/lumen/
	$(CP) $(PKG_BUILD_DIR)/lib/*.lua 							$(1)/usr/lib/lua/lumen/lib
	$(CP) $(PKG_BUILD_DIR)/tasks/*.lua 							$(1)/usr/lib/lua/lumen/tasks
	$(CP) $(PKG_BUILD_DIR)/tasks/http-server/*.lua 				$(1)/usr/lib/lua/lumen/tasks/http-server
	$(CP) $(PKG_BUILD_DIR)/tasks/http-server/websocket/*.lua	$(1)/usr/lib/lua/lumen/tasks/http-server/websocket
	$(CP) $(PKG_BUILD_DIR)/tasks/http-server/www/* 				$(1)/usr/lib/lua/lumen/tasks/http-server/www


endef

$(eval $(call BuildPackage,lua-lumen))