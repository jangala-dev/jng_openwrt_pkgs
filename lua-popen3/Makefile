include $(TOPDIR)/rules.mk

PKG_NAME:=lua-popen3
PKG_VERSION:=0.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/jangala-dev/lua-popen3/tar.gz/refs/tags/$(PKG_VERSION)?
PKG_HASH:=e281d039392fcb3251d0a3b6a3685e6751e736a1b055d2d3426b099dab183324
PKG_BUILD_DIR:=$(BUILD_DIR)/lua-popen3-$(PKG_VERSION)

PKG_MAINTAINER:=Rich <rich@janga.la>
PKG_LICENSE:=MIT

include $(INCLUDE_DIR)/package.mk

define Package/lua-popen3
	SUBMENU:=Lua
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=lua-popen3
	DEPENDS:=+lua +luaposix
	PKGARCH:=all
endef

define Package/lua-popen3/description
	Utilties for using Lua with external commands.
endef

define Build/Configure
endef

define Build/Compile
endef

define Build/Install
endef

define Package/lua-popen3/install
	$(INSTALL_DIR) $(1)/usr/lib/lua

	$(CP) $(PKG_BUILD_DIR)/popen3.lua 	$(1)/usr/lib/lua/
	$(CP) $(PKG_BUILD_DIR)/pipe.lua 	$(1)/usr/lib/lua/
endef

$(eval $(call BuildPackage,lua-popen3))