include $(TOPDIR)/rules.mk

PKG_NAME:=lua-binaryheap
PKG_VERSION:=version_0v4
PKG_RELEASE:=1

PKG_SOURCE:=binaryheap.lua-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:= https://codeload.github.com/Tieske/binaryheap.lua/tar.gz/refs/tags/$(PKG_VERSION)?
PKG_HASH:=10b1b6c6f2d22560f512f9896a6672ec5ae0eea1390ff8e662be1d5d9625b438
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

PKG_MAINTAINER:=Rich <rich@janga.la>
PKG_LICENSE:=MIT

include $(INCLUDE_DIR)/package.mk

define Package/lua-binaryheap
	SUBMENU:=Lua
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=lua-binaryheap
	DEPENDS:=+lua
	PKGARCH:=all
endef

define Package/lua-binaryheap/description
	Binary heap implementation in lua
endef

define Build/Compile
	echo "Nothing to compile, pure lua package"
endef

define Package/lua-binaryheap/install
	$(INSTALL_DIR) $(1)/usr/lib/lua/
	$(INSTALL_DIR) $(1)/usr/lib/lua/binaryheap

	$(CP) $(PKG_BUILD_DIR)/src/*.lua 	$(1)/usr/lib/lua/binaryheap/
endef

$(eval $(call BuildPackage,lua-binaryheap))