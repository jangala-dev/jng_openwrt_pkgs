include $(TOPDIR)/rules.mk

PKG_NAME:=libubootenv
PKG_VERSION:=v0.3.1
PKG_RELEASE:=2

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/sbabic/libubootenv.git
PKG_SOURCE_VERSION:=824551ac77bab1d0f7ae34d7a7c77b155240e754
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
