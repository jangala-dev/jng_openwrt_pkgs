include $(TOPDIR)/rules.mk

PKG_NAME:=qfirehose
PKG_VERSION:=1.4.21
PKG_RELEASE:=1

PKG_MAINTAINER:=Quectel <support@quectel.com>
PKG_LICENSE:=Proprietary
PKG_LICENSE_FILES:=LICENSE

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
include $(INCLUDE_DIR)/package.mk

define Package/qfirehose
    SECTION:=utils
    CATEGORY:=Utilities
    TITLE:=QFirehose Tool
    DEPENDS:=+libpthread
endef

define Package/qfirehose/description
    QFirehose tool for firmware flashing via USB.
endef

TARGET_CFLAGS += -Wall -Wextra -Werror -g
TARGET_LDFLAGS += -lpthread -ldl

define Build/Configure
endef

define Build/Prepare
    mkdir -p $(PKG_BUILD_DIR)
    $(CP) ./$(PKG_NAME)-$(PKG_VERSION)/* $(PKG_BUILD_DIR)/
endef

define Build/Compile
    $(TARGET_CC) $(TARGET_CFLAGS) $(TARGET_CPPFLAGS) \
        $(PKG_BUILD_DIR)/firehose_protocol.c \
        $(PKG_BUILD_DIR)/qfirehose.c \
        $(PKG_BUILD_DIR)/sahara.c \
        $(PKG_BUILD_DIR)/usb_linux.c \
        $(PKG_BUILD_DIR)/stream_download_protocol.c \
        $(PKG_BUILD_DIR)/md5.c \
        $(PKG_BUILD_DIR)/usb2tcp.c \
        -o $(PKG_BUILD_DIR)/qfirehose \
        $(TARGET_LDFLAGS)
endef

define Package/qfirehose/install
    $(INSTALL_DIR) $(1)/usr/bin
    $(INSTALL_BIN) $(PKG_BUILD_DIR)/qfirehose $(1)/usr/bin/
endef

$(eval $(call BuildPackage,qfirehose))