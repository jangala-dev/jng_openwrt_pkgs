#Owned by DairyMan@Whirlpool
#
#Copyright GNU act.
include $(TOPDIR)/rules.mk

PKG_NAME:=we826q-wd-script
PKG_VERSION:=1.000
PKG_RELEASE:=1

PKG_MAINTAINER:=Created by DM/makefile by Cobia@whirlpool
include $(INCLUDE_DIR)/package.mk

define Package/we826q-wd-script
  SECTION:=utils
  CATEGORY:=JNG device specific
  SUBMENU:=WE826-Q
  TITLE:=A simple script to prevent watchdog induced reboot
  PKGARCH:=all
endef

define Package/we826q-wd-script/description

endef


define Build/Compile
endef

define Package/we826q-wd-script/install
        $(CP) ./files/* $(1)/


endef

$(eval $(call BuildPackage,we826q-wd-script))
