include $(TOPDIR)/rules.mk

PKG_NAME:=atinout
PKG_VERSION:=v0.9.1
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/beralt/atinout.git
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_VERSION:=4013e8db4cd140c1df24bb90f929efeb9b61b238

PKG_MAINTAINER:=Wambui Karuga <wambui@janga.la>

include $(INCLUDE_DIR)/package.mk

define Package/atinout
	SECTION:=core
	CATEGORY:=JNG
	TITLE:=Atinout
endef

define Package/atinout/description
Atinout is a program that will execute AT commands in sequence and
capture the response from the modem.
endef

CONFIGURE_VARS += \
  CC="$(TARGET_CC)" \
  CXX="$(TARGET_CC) +.c++" \
  CFLAGS="$(TARGET_CFLAGS) -Wall -DVERSION=\"\\\"$(PKG_VERSION)\\\"\"" \
  LDFLAGS="$(TARGET_LDFLAGS)"

define Build/Configure
	$(call Build/Configure/Default,--with-linux-headers=$(LINUX_DIR))
endef

define Build/Compile
	@echo -e "\n=== Build/Compile ==="
	$(CONFIGURE_VARS) $(MAKE) -C $(PKG_BUILD_DIR) \
		all \

endef

define Package/atinout/install
	$(INSTALL_DIR) $(1)/usr/bin

	$(INSTALL_BIN) $(PKG_BUILD_DIR)/atinout $(1)/usr/bin/atinout
endef

define Package/atinout/postinst
	#!/bin/sh
	[ -n "$${IPKG_INST_ROOT}" ] && exit 0
	exit 0
endef

$(eval $(call BuildPackage,atinout))