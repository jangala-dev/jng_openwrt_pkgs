include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_VERSION:=2020.04
PKG_RELEASE:=1

PKG_HASH:=fe732aaf037d9cc3c0909bad8362af366ae964bbdac6913a34081ff4ad565372

include $(INCLUDE_DIR)/u-boot.mk
include $(INCLUDE_DIR)/package.mk

define U-Boot/Default
  BUILD_TARGET:=ath79
  UBOOT_IMAGE:=u-boot.bin
endef

define U-Boot/ap143
	BUILD_DEVICES:=ap143
	NAME:=AP143 Reference Board
	UBOOT_CONFIG:=ap143
endef

define U-Boot/get-box
	BUILD_DEVICES:=jangala_get-box
	NAME:=Jangala Get-Box
	UBOOT_CONFIG:=get-box
endef

UBOOT_TARGETS := \
	ap143 \
	get-box

define Build/InstallDev
	$(INSTALL_DIR) $(STAGING_DIR_IMAGE)
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/$(UBOOT_IMAGE) $(STAGING_DIR_IMAGE)/$(VARIANT)-$(UBOOT_IMAGE)
endef

$(eval $(call BuildPackage/U-Boot))