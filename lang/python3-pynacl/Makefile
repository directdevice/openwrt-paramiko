include $(TOPDIR)/rules.mk

PKG_NAME:=python3-pynacl
PKG_VERSION:=1.3.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://github.com/pyca/pynacl/archive
PKG_MD5SUM:=cb6560512d1d2300b3ddbe1a1daf871d

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
HOST_PYTHON3_PACKAGE_BUILD_DEPENDS:="cffi>=1.4.1"

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

PYTHON3_PKG_SETUP_VARS:= SODIUM_INSTALL=system

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python3-pynacl
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=Networking and Cryptography (NaCl) library
  URL:=https://pynacl.readthedocs.io/en/stable/
  DEPENDS:= \
    +libsodium @!LIBSODIUM_MINIMAL \
    +PACKAGE_python3-bcrypt:python3-light \
    +PACKAGE_python3-bcrypt:python3-cffi \
    +PACKAGE_python3-bcrypt:python3-six
  VARIANT:=python3
endef

define Package/python3-pynacl/description
  Fork of the Networking and Cryptography library
endef

$(eval $(call Py3Package,$(PKG_NAME)))
$(eval $(call BuildPackage,$(PKG_NAME)))