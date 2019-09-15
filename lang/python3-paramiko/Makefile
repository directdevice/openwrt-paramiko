include $(TOPDIR)/rules.mk

PKG_NAME:=python3-paramiko
PKG_VERSION:=2.6.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://github.com/paramiko/paramiko/archive
PKG_MD5SUM:=161c71e27076eb1f2fc2fb2705d95a45

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_BUILD_DEPENDS:=python3

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python3-paramiko
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=python3-paramiko
  URL:=https://github.com/paramiko/paramiko
  DEPENDS:= \
    +PACKAGE_python3-paramiko:python3 \
    +PACKAGE_python3-paramiko:python3-cryptography \
    +PACKAGE_python3-paramiko:python3-pynacl \
    +PACKAGE_python3-paramiko:python3-bcrypt
  VARIANT:=python3
endef

define Package/python3-paramiko/description
 Native Python SSHv2 protocol library 
endef

$(eval $(call Py3Package,$(PKG_NAME))
$(eval $(call BuildPackage,$(PKG_NAME))