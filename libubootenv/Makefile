include $(TOPDIR)/rules.mk

PKG_NAME:=libubootenv
PKG_VERSION:=0.3.2
PKG_RELEASE:=$(AUTORELEASE)

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/sbabic/libubootenv/archive/v$(PKG_VERSION)
PKG_HASH:=662ef1efe058e2d5a07498f7b63aff7b2a521c0f6f199c499fb3ae84b54121bd

PKG_MAINTAINER:=Wambui Karuga <wambui@janga.la>

CMAKE_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

CMAKE_OPTIONS += -DBUILD_DOC=OFF

define Package/libubootenv
	SECTION:=libs
	CATEGORY:=Libraries
	TITLE:=U-Boot Environment Access
	DEPENDS:=+zlib
endef

define Package/libubootenv/description
	Libubootenv is a library that provides a hardware independent way to access to U-Boot environment.
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig $(1)/usr/include/

	$(CP) $(PKG_BUILD_DIR)/src/libuboot.h $(1)/usr/include/
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/src/libubootenv.a $(1)/usr/lib/
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/libubootenv.pc $(1)/usr/lib/pkgconfig
endef

define Package/libubootenv/install
	$(INSTALL_DIR) $(1)/usr/bin/
	$(INSTALL_DIR) $(1)/usr/lib/

	$(INSTALL_DATA) $(PKG_BUILD_DIR)/src/libubootenv.so* $(1)/usr/lib/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/{fw_printenv,fw_setenv} $(1)/usr/bin/
endef

$(eval $(call BuildPackage,libubootenv))
