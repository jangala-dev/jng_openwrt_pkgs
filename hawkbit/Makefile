include $(TOPDIR)/rules.mk

PKG_NAME:=hawkbit
PKG_VERSION:=v0.0.1
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/rauc/rauc-hawkbit-updater
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).$(PKG_RELEASE).tar.gz
PKG_SOURCE_VERSION:=b38f5a580ab66845d7376b276c80da4b2396337d

PKG_MAINTAINER:=Wambui Karuga <wambui@janga.la>

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Build/Prepare
	$(Build/Prepare/Default)
endef

define Package/hawkbit
        SECTION:=core
        CATEGORY:=JNG
        TITLE:=RAUC Hawkbit Updater
	DEPENDS:=+json-glib \
		+libiconv-full \
		+libcurl \
		+rauc
endef

CMAKE_OPTIONS += -DWITH_SYSTEMD=OFF
TARGET_LDFLAGS += \
	-L$(STAGING_DIR)/usr/lib/libiconv-full/lib/

MAKE_FLAGS += \
        CFLAGS="$(TARGET_CFLAGS)" \
	LDFLAGS="$(TARGET_LDFLAGS)"

define Package/hawkbit/description
The RAUC hawkBit updater is a simple commandline tool/daemon that runs on your target and operates as an interface between the RAUC D-Bus API and the hawkBit DDI API.
endef

define Package/hawkbit/install
	$(INSTALL_DIR) $(1)/usr/bin/

	$(INSTALL_BIN) $(PKG_BUILD_DIR)/rauc-hawkbit-updater $(1)/usr/bin/
endef

$(eval $(call BuildPackage,hawkbit))
