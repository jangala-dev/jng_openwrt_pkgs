include $(TOPDIR)/rules.mk

PKG_NAME:=uqmi
PKG_RELEASE:=9

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL=git@github.com:wambu-i/uqmi.git
PKG_SOURCE_DATE:=2021-05-20
PKG_SOURCE_VERSION:=1f29792315f5f68caef61c615973912ea248558b
#PKG_MIRROR_HASH:=3c39b1c1f20b7d523b0891d08b3d10233331ada8e11d0b55cfd4882816308951
PKG_MAINTAINER:=Wambui Karuga <wambui@janga.la>

PKG_LICENSE:=GPL-2.0
PKG_LICENSE_FILES:=

PKG_BUILD_PARALLEL:=1

PKG_FLAGS:=nonshared

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/uqmi
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=JNG
  DEPENDS:=+libubox +libblobmsg-json +kmod-usb-net +kmod-usb-net-qmi-wwan +wwan
  TITLE:=Control utility for mobile broadband modems
endef

define Package/uqmi/description
  uqmi is a command line tool for controlling mobile broadband modems using
  the QMI-protocol.
endef

TARGET_CFLAGS += \
	-I$(STAGING_DIR)/usr/include -ffunction-sections -fdata-sections

TARGET_LDFLAGS += -Wl,--gc-sections

CMAKE_OPTIONS += \
	-DDEBUG=1

define Package/uqmi/install
	$(INSTALL_DIR) $(1)/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/uqmi $(1)/sbin/
	$(CP) ./files/* $(1)/
endef

$(eval $(call BuildPackage,uqmi))