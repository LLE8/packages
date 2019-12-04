# 
# This is free software, licensed under the GNU General Public License v2.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=ipfs-http-client
PKG_RELEASE:=1

PKG_MAINTAINER:=Leonid Esman <leonid.esman@gmail.com>
PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE.MIT

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/vasild/cpp-ipfs-http-client.git
#PKG_SOURCE_DATE:=2019-11-05
PKG_SOURCE_VERSION:=763e59ad698f3e3846f85df11e01c18ef3fbc401
PKG_MIRROR_HASH:=39b7118452c33782f0a370fce1e9b8e1b75dfe2f75bbf4c850d6886685d82a3e

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)/Default/description
	IPFS (the InterPlanetary File System) is the Distributed Web, 
	specs, docs, sources, links https://ipfs.io/ and https://github.com/ipfs
	This is Vasil Dimov's C++ IPFS HTTP API client library
	https://github.com/vasild/cpp-ipfs-http-client
endef

define Package/lib$(PKG_NAME)
	SECTION:=libs
	CATEGORY:=Libraries
	TITLE:=IPFS client library
	URL:=https://github.com/vasild/cpp-ipfs-http-client
	DEPENDS:= +libcurl +libstdcpp
	PKG_BUILD_DEPENDS:=nlohmannjson
endef

define Package/lib$(PKG_NAME)/description
	$(call Package/$(PKG_NAME)/Default/description)
	This package contains shared library.
endef

define Package/$(PKG_NAME)-tests
	SECTION:=utils
	CATEGORY:=Utilities
	TITLE:=IPFS client library tests
	URL:=https://github.com/vasild/cpp-ipfs-http-client
	DEPENDS:=+libipfs-http-client +libcurl
endef

define Package/$(PKG_NAME)-tests/description
	$(call Package/$(PKG_NAME)/Default/description)
	This package contains library tests.
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_BUILD_DIR)/include/* $(1)/usr/include
	$(CP) $(PKG_BUILD_DIR)/libipfs-http-client.a $(1)/usr/lib
endef

define Package/lib$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_BUILD_DIR)/libipfs-http-client.so* $(1)/usr/lib
endef

define Package/$(PKG_NAME)-tests/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/test/ipfs-* $(1)/usr/bin
endef

$(eval $(call BuildPackage,lib$(PKG_NAME)))
$(eval $(call BuildPackage,$(PKG_NAME)-tests))

