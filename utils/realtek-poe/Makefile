## SPDX-License-Identifier: GPL-2.0-or-later

include $(TOPDIR)/rules.mk

PKG_NAME:=realtek-poe
PKG_RELEASE:=1
PKG_LICENSE:=GPL-2.0
PKG_MAINTAINER:=Martin Kennedy <hurricos@gmail.com>

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/Hurricos/realtek-poe.git
PKG_SOURCE_VERSION:=2df137ee45715533c1aae81ccc41e5eb8fb763f6
PKG_MIRROR_HASH:=24b00f216f4f5fcce6de49fd4088549205d0e33440d276a745348f7c31206407
CMAKE_SOURCE_SUBDIR:=src

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/realtek-poe
  SECTION:=net
  CATEGORY:=Network
  TITLE:=Realtek PoE Switch Port daemon
  DEPENDS:=@TARGET_realtek +libubox +libubus +libuci
endef

define Package/realtek-poe/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_DIR) $(1)/etc/uci-defaults
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/realtek-poe $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/files/etc/init.d/poe $(1)/etc/init.d/
	$(INSTALL_CONF) $(PKG_BUILD_DIR)/files/etc/config/poe $(1)/etc/config/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/files/etc/uci-defaults/30-poe $(1)/etc/uci-defaults/30-poe
endef

$(eval $(call BuildPackage,realtek-poe))
