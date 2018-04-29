#
# Copyright (C) 2009-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python-crypto
PKG_VERSION:=2.6
PKG_RELEASE:=1

PKG_SOURCE:=v$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://github.com/dlitz/pycrypto/archive
PKG_MD5SUM:=9e24388059cd9a4acf989cac4b5fff8e

PKG_BUILD_DIR:=$(BUILD_DIR)/pycrypto-$(PKG_VERSION)
PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-crypto
	SECTION:=lang-python
	CATEGORY:=Languages
	SUBMENU:=Python
	TITLE:=python-crypto
	URL:=http://www.pycrypto.org/
	DEPENDS:=+python +libgmp
endef

define Package/python-crypto/description
A collection of both secure hash functions (such as MD5 and SHA),
and various encryption algorithms (AES, DES, IDEA, RSA, ElGamal, etc.).
endef

define Build/Compile
	$(call Build/Compile/PyMod,., \
		install --prefix="/usr" --root="$(PKG_INSTALL_DIR)" \
	)
endef

define Package/python-crypto/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,python-crypto))