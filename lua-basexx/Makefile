include $(TOPDIR)/rules.mk

PKG_NAME:=lua-basexx
PKG_VERSION:=0.4.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/aiq/basexx/tar.gz/refs/tags/v$(PKG_VERSION)?
PKG_HASH:=ff62b00446df1181a9cd20ba970c3c8493165d262142e10d069ee3de6337dfe6
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

PKG_MAINTAINER:=Rich <rich@janga.la>
PKG_LICENSE:=MIT

include $(INCLUDE_DIR)/package.mk

define Package/lua-basexx
	SUBMENU:=Lua
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=lua-basexx
	DEPENDS:=+lua
	PKGARCH:=all
endef

define Package/lua-basexx/description
	A Lua library for base2, base16, base32, base64, base85 decoding and encoding of data strings.
endef

define Build/Compile
	echo "Nothing to compile, pure lua package"
endef

define Package/lua-basexx/install
	$(INSTALL_DIR) $(1)/usr/lib/lua/
	$(INSTALL_DIR) $(1)/usr/lib/lua/basexx

	$(CP) $(PKG_BUILD_DIR)/lib/*.lua 	$(1)/usr/lib/lua/basexx/
endef

$(eval $(call BuildPackage,lua-basexx))