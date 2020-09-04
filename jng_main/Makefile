include $(TOPDIR)/rules.mk

PKG_NAME:=jng-main
PKG_VERSION:=0.0.2
PKG_RELEASE:=2

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=git@bitbucket.org:jangala/main.git
PKG_SOURCE_DATE:=2020-09-04
PKG_SOURCE_VERSION:=d5ee78f1cd1505cba1b2eec786a9341d1f5acfcc

PKG_MAINTAINER:=Richard Thanki <rich@janga.la>

include $(INCLUDE_DIR)/package.mk

define Package/jng-main
	SECTION:=core
	CATEGORY:=JNG
	TITLE:=Get Box Main
	DEPENDS:=+luasocket \
		+luabitop \
		+luaposix \
		+dkjson \
		+lua-openssl \
		+lua-lumen
endef

define Package/jng-main/description
	This program is provides various run time for Get Box such as:
	unlocking/locking the sim card setting up Wi-Fi and DHCP gathering and publishing statistics to the cloud.
endef

define Build/Compile
endef

define Package/jng-main/install
	$(INSTALL_DIR) $(1)/root/getboxtoy/main
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_DIR) $(1)/etc/jng/words

	$(INSTALL_BIN) $(PKG_BUILD_DIR)/getbox.lua $(1)/root/getboxtoy/main/getbox
	$(CP) $(PKG_BUILD_DIR)/config.default $(1)/root/getboxtoy/main
	$(CP) $(PKG_BUILD_DIR)/modules $(1)/root/getboxtoy/main
	$(CP) $(PKG_BUILD_DIR)/etc $(1)/root/getboxtoy/main/
	$(INSTALL_BIN) ./files/getbox.init $(1)/etc/init.d/getbox
	$(CP) ./files/words/* $(1)/etc/jng/words/
endef

define Package/jng-main/postinst
	#!/bin/sh
	[ -n "$${IPKG_INST_ROOT}" ] && exit 0

	if ! /etc/init.d/getbox enabled; then
		/etc/init.d/getbox enable
	fi

	/etc/init.d/getbox restart 2>/dev/null
	exit 0
endef

$(eval $(call BuildPackage,jng-main))