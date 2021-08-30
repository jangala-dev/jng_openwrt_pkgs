include $(TOPDIR)/rules.mk

PKG_NAME:=lua-http
PKG_VERSION:=0.4
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/daurnimator/lua-http/tar.gz/refs/tags/v$(PKG_VERSION)?
PKG_HASH:=d2e3cb9bc04cab70ac4f19351bc74b0dcd8b16cfc2563aa77256eb3a43b3b9e0
# PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

PKG_MAINTAINER:=Rich <rich@janga.la>
PKG_LICENSE:=MIT

include $(INCLUDE_DIR)/package.mk

define Package/lua-http
	SUBMENU:=Lua
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=lua-http
	DEPENDS:=+lua +lua-cqueues +luaossl +lua-basexx +lpeg +lpeg_patterns +lua-binaryheap +lua-fifo
	PKGARCH:=all
endef

define Package/lua-http/description
	lua-http is a performant, capable HTTP and WebSocket library for Lua 5.1, 5.2, 5.3 and LuaJIT.
endef

define Build/Configure
endef

define Build/Compile
endef

define Package/lua-http/install
	$(INSTALL_DIR) $(1)/usr/lib/lua
	
	$(CP) $(PKG_BUILD_DIR)/http					$(1)/usr/lib/lua
endef

$(eval $(call BuildPackage,lua-http))