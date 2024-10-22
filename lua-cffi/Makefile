#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=cffi-lua
PKG_VERSION:=0.2.3
PKG_RELEASE:=1


PKG_SRC_NAME:=lua-somthing
PKG_SRC_VERSION:=0.2.3
PKG_SOURCE_URL=https://codeload.github.com/q66/cffi-lua/archive/refs/tags/v$(PKG_SRC_VERSION).tar.gz
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_HASH:=1d2577a62a843e5e6db35af1b58300d279b4df58eccef5e823441501f960d388
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_SRC_VERSION)

PKG_MAINTAINER:=Nina <me@q66.moe>
PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE

PKG_BUILD_DEPENDS:=luarocks/host

include $(INCLUDE_DIR)/package.mk

define Package/lua-cffi
	SUBMENU:=Lua
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=Lua 5.1+ c mounting library
	DEPENDS:=+lua
endef

define Package/lua-cffi/description
	C mounting for lua
endef

TARGET_CFLAGS += \
	-I$(STAGING_DIR)/usr/include

define Build/Compile
	cd $(PKG_BUILD_DIR) && \
	luarocks make --pack-binary-rock $(PKG_BUILD_DIR)/cffi-lua-0.2.3-1.rockspec \
	LUA_LIBDIR=$(STAGING_DIR)/usr/lib/lua \
	LUA_PKGNAME=lua5.1 \
	CFLAGS="$(TARGET_CFLAGS) $(FPIC)" \
	LDFLAGS="$(TARGET_LDFLAGS)" \
	CC="$(TARGET_CC)" LD="$(TARGET_CC)"
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/lib/lua
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/cffi.so $(1)/usr/lib/lua
endef

$(eval $(call BuildPackage,lua-cffi))
