include $(TOPDIR)/rules.mk

PKG_NAME:=lua-http
PKG_VERSION:=0.4
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/daurnimator/lua-http/tar.gz/refs/tags/v$(PKG_VERSION)?
PKG_HASH:=d2e3cb9bc04cab70ac4f19351bc74b0dcd8b16cfc2563aa77256eb3a43b3b9e0
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

PKG_MAINTAINER:=Rich <rich@janga.la>
PKG_LICENSE:=MIT

PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/lua-http
	SECTION:=core
	CATEGORY:=JNG
	TITLE:=lua-http
	DEPENDS:=+lua +lua-cqueues +luaossl +lua-basexx +lpeg +lpeg_patterns +lua-binaryheap +lua-fifo
endef

define Package/lua-http/description
	lua-http is an performant, capable HTTP and WebSocket library for Lua 5.1, 5.2, 5.3 and LuaJIT.
endef

define Build/Compile
	echo "Nothing to compile, pure lua package"
endef

define Package/lua-http/install
	$(INSTALL_DIR) $(1)/usr/lib/lua/
	$(INSTALL_DIR) $(1)/usr/lib/lua/http
	$(INSTALL_DIR) $(1)/usr/lib/lua/http/compat

	$(CP) $(PKG_BUILD_DIR)/http/*.lua 					$(1)/usr/lib/lua/http/
	$(CP) $(PKG_BUILD_DIR)/http/compat/*.lua 			$(1)/usr/lib/lua/http/compat
endef

$(eval $(call BuildPackage,lua-http))