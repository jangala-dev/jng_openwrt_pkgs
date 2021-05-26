include $(TOPDIR)/rules.mk

PKG_NAME:=lua-lumen
PKG_VERSION:=0.0.1
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=git@github.com:xopxe/lumen.git
PKG_SOURCE_DATE:=2020-07-07
PKG_SOURCE_VERSION:=6011a0676416bd8b63ddd9ffe2d48a0742cbb472
PKG_SOURCE_SUBDIR:=$(PKG_NAME)

PKG_MAINTAINER:=Jorge <xxopxe@gmail.com>

include $(INCLUDE_DIR)/package.mk

define Package/lua-lumen
	SECTION:=core
	CATEGORY:=JNG
	TITLE:=Lumen
endef

define Package/lua-lumen/description
	Lumen is a very simple environment for coroutine based multitasking.
endef

define Build/Compile
endef

define Package/lua-lumen/install
	$(INSTALL_DIR) $(1)/usr/lib/lua/
	$(INSTALL_DIR) $(1)/usr/lib/lua/lumen

	$(CP) $(BUILD_DIR)/$(PKG_SOURCE_SUBDIR)/* $(1)/usr/lib/lua/lumen/
endef

$(eval $(call BuildPackage,lua-lumen))