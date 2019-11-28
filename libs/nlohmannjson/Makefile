#
# This is free software, licensed under the GNU General Public License v2.
#

##  NLohmann JSON C++ lib for OpenWrt, Nov 2019

include $(TOPDIR)/rules.mk

PKG_NAME:=nlohmannjson
PKG_VERSION:=3.7.3
PKG_RELEASE:=1

PKG_SOURCE:=json-$(PKG_VERSION).zip
PKG_SOURCE_URL:=https://codeload.github.com/nlohmann/json/zip/v$(PKG_VERSION)?
PKG_HASH:=e109cd4a9d1d463a62f0a81d7c6719ecd780a52fb80a22b901ed5b6fe43fb45b


PKG_BUILD_DIR:=$(BUILD_DIR)/json-$(PKG_VERSION)


include $(INCLUDE_DIR)/package.mk


define Package/nlohmannjson
	SECTION:=libs
	CATEGORY:=Libraries
	DEPENDS:=
	TITLE:=JSON for Modern C++
	URL:=https://nlohmann.github.io/json/
	MAINTAINER:=
endef


define Package/nlohmannjson/description
	Niels Lohmann's JSON library for modern C++
endef


define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_BUILD_DIR)/include/nlohmann $(1)/usr/include
endef


$(eval $(call BuildPackage,nlohmannjson))

