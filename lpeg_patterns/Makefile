include $(TOPDIR)/rules.mk

PKG_NAME:=lpeg_patterns
PKG_VERSION:=0.5
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/daurnimator/lpeg_patterns/tar.gz/refs/tags/v$(PKG_VERSION)?
PKG_HASH:=d1fabf897024822eb2544fd811fc80b85655972804511b9fd8cfea377fb16e0e
# PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

PKG_MAINTAINER:=Rich <rich@janga.la>
PKG_LICENSE:=MIT

include $(INCLUDE_DIR)/package.mk

define Package/lpeg_patterns
	SUBMENU:=Lua
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=LPeg Patterns
	DEPENDS:=+lua +lpeg
	PKGARCH:=all
endef

define Package/lpeg_patterns/description
	A collection of LPeg patterns.
endef

define Build/Configure
endef

define Build/Compile
endef

define Build/Install
endef

define Package/lpeg_patterns/install
	$(INSTALL_DIR) $(1)/usr/lib/lua
	
	$(CP) $(PKG_BUILD_DIR)/lpeg_patterns $(1)/usr/lib/lua/
endef

$(eval $(call BuildPackage,lpeg_patterns))