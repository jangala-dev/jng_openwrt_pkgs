include $(TOPDIR)/rules.mk

PKG_NAME:=lua-fifo
PKG_VERSION:=0.2
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/daurnimator/fifo.lua/tar.gz/refs/tags/$(PKG_VERSION)?
PKG_HASH:=85cad0c2f9eac1cd3e08c5134feb655e0b928e1e22363c3ef3293a194c0eb53f
PKG_BUILD_DIR:=$(BUILD_DIR)/fifo.lua-$(PKG_VERSION)

PKG_MAINTAINER:=Rich <rich@janga.la>
PKG_LICENSE:=MIT

include $(INCLUDE_DIR)/package.mk

define Package/lua-fifo
	SUBMENU:=Lua
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=lua-fifo
	DEPENDS:=+lua
	PKGARCH:=all
endef

define Package/lua-fifo/description
	A lua library/'class' that implements a FIFO. Objects in the fifo can be of any type, including nil.
endef

define Build/Configure
endef

define Build/Compile
endef

define Build/Install
endef

define Package/lua-fifo/install
	$(INSTALL_DIR) $(1)/usr/lib/lua

	$(CP) $(PKG_BUILD_DIR)/*.lua 	$(1)/usr/lib/lua/
endef

$(eval $(call BuildPackage,lua-fifo))