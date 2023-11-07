include $(TOPDIR)/rules.mk

PKG_NAME:=swupdate
PKG_VERSION:=2021.04
PKG_RELEASE:=$(AUTORELEASE)

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/sbabic/swupdate/archive/$(PKG_VERSION)
PKG_HASH:=5afe78ae94e869bcb911d8592251641cdab80096d8e5149d483054ea49f9aab8

PKG_MAINTAINER:=Wambui Karuga <wambui@janga.la>

PKG_BUILD_DEPENDS:=mtd-utils
include $(INCLUDE_DIR)/package.mk

define Build/Prepare
	$(Build/Prepare/Default)
	$(INSTALL_DIR) $(STAGING_DIR)/usr/include/mtd/
	$(CP) -R $(TOPDIR)/build_dir/host/mtd-utils-*/include/* $(STAGING_DIR)/usr/include/
endef

define Package/swupdate
	SECTION:=core
	CATEGORY:=JNG
	TITLE:=SWUpdate
	DEPENDS:=+ubi-utils +libconfig +liblua +libubootenv +libcurl +libjson-c  +zlib
endef

TARGET_CFLAGS += \
	-I$(STAGING_DIR)/usr/include/mtd \
	-I$(STAGING_DIR)/usr/include/mtd/mtd \
	-I$(STAGING_DIR)/usr/include
TARGET_LDFLAGS += \
	-L$(BUILD_DIR)/mtd-utils-*

MAKE_FLAGS += \
	CFLAGS="$(TARGET_CFLAGS)" \
	LDFLAGS="$(TARGET_LDFLAGS)"

define Package/swupdate/description
SWUpdate is a Linux Update agent with the goal to provide an efficient and safe way to update an embedded system.
SWUpdate supports local and remote updates, and multiple update strategies.
endef

define Build/Configure
	$(CP) ./files/swupdate.config $(PKG_BUILD_DIR)/.config
endef

define Package/swupdate/install
	$(INSTALL_DIR) $(1)/usr/bin/

	$(INSTALL_BIN) $(PKG_BUILD_DIR)/swupdate $(1)/usr/bin/swupdate
endef

$(eval $(call BuildPackage,swupdate))
