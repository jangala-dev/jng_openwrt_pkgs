#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=lua-compat53
PKG_VERSION:=0.8
PKG_RELEASE:=1


PKG_SRC_NAME:=lua-compat-5.3
PKG_SRC_VERSION:=0.8
PKG_SOURCE_URL=https://codeload.github.com/keplerproject/$(PKG_SRC_NAME)/tar.gz/refs/tags/v$(PKG_SRC_VERSION)?
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_HASH:=97cc1c1d94e128969c2acbef47ce162d856bafd6c72674e7f7530f9ef97e07c3
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_SRC_NAME)-$(PKG_SRC_VERSION)

PKG_MAINTAINER:=Rich Thanki <rich@janga.la>
PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE

PKG_BUILD_DEPENDS:=luarocks/host

include $(INCLUDE_DIR)/package.mk

define Package/lua-compat53
  SUBMENU:=Lua
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=Lua-5.3-style APIs for Lua 5.2 and 5.1.
  DEPENDS:=+lua
endef

define Package/lua-compat53/description
  This is a small module that aims to make it easier to write code in a 
  Lua-5.3-style that is compatible with Lua 5.1, Lua 5.2, and Lua 5.3. 
  This does not make Lua 5.2 (or even Lua 5.1) entirely compatible with Lua 
  5.3, but it brings the API closer to that of Lua 5.3.
endef

TARGET_CFLAGS += \
	-I$(STAGING_DIR)/usr/include

define Build/Compile
  cd $(PKG_BUILD_DIR) && \
  luarocks make --pack-binary-rock rockspecs/compat53-scm-0.rockspec \
	LUA_LIBDIR=$(STAGING_DIR)/usr/lib/lua \
	LUA_PKGNAME=lua5.1 \
	CFLAGS="$(TARGET_CFLAGS) $(FPIC)" \
	LDFLAGS="$(TARGET_LDFLAGS)" \
	CC="$(TARGET_CC)" LD="$(TARGET_CC)"
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/lib/lua
  $(INSTALL_DIR) $(1)/usr/lib/lua/compat53

  $(CP) $(PKG_BUILD_DIR)/compat53/* $(1)/usr/lib/lua/compat53
endef

$(eval $(call BuildPackage,lua-compat53))
