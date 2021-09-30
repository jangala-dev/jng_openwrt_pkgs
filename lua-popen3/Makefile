include $(TOPDIR)/rules.mk

PKG_NAME:=lua-popen3
PKG_VERSION:=1.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/jangala-dev/lua-popen3/tar.gz/refs/tags/v$(PKG_VERSION)?
PKG_HASH:=4bc421c688e3b61363f74031dbf29ef1484b08189485e5188578c38eb8717d13
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