#
# Copyright (C) 2018 Onion Corporation
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=bettercap
PKG_VERSION:=0.1
PKG_RELEASE:=1

PKG_SOURCE_URL=https://github.com/ahayden/bettercap.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=HEAD
PKG_SOURCE_SUBDIR:=$(PKG_NAME)
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)


include $(INCLUDE_DIR)/package.mk


define Package/bettercap
	SECTION:=onion
	CATEGORY:=Onion
	SUBMENU:=Utilities
	TITLE:=Bettercap
	DEPENDS:=+libpcap 
endef


TARGET_LIB += -lcurl
TARGET_CFLAGS += $(FPIC) 


define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR) \
	CC="$(TARGET_CC)" \
	CFLAGS="$(TARGET_CFLAGS)" \
	LDFLAGS="$(TARGET_LDFLAGS)" \
	LIB="$(TARGET_LIB)"
endef

define Package/bettercap/install
	PREFIX=$(INSTALL_DIR) make install
endef


$(eval $(call BuildPackage,bettercap))
