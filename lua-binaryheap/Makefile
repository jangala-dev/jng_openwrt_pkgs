include $(TOPDIR)/rules.mk

PKG_NAME:=binaryheap
PKG_VERSION:=version_0v4
PKG_RELEASE:=1

PKG_SOURCE:=git
PKG_SOURCE_URL:= https://codeload.github.com/Tieske/binaryheap.lua/tar.gz/refs/tags/$(PKG_VERSION)?
PKG_HASH:=10b1b6c6f2d22560f512f9896a6672ec5ae0eea1390ff8e662be1d5d9625b438
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

PKG_MAINTAINER:=Rich <rich@janga.la>
PKG_LICENSE:=MIT

PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/binaryheap
	SECTION:=core
	CATEGORY:=JNG
	TITLE:=binaryheap
	DEPENDS:=+lua
endef

define Package/binaryheap/description
	Binary heap implementation in lua
endef

define Build/Compile
	echo "Nothing to compile, pure lua package"
endef

define Package/binaryheap/install
	$(INSTALL_DIR) $(1)/usr/lib/lua/
	$(INSTALL_DIR) $(1)/usr/lib/lua/binaryheap

	$(CP) $(PKG_BUILD_DIR)/src/*.lua 					$(1)/usr/lib/lua/binaryheap/
endef

$(eval $(call BuildPackage,binaryheap))