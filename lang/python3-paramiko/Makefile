include $(TOPDIR)/rules.mk

PKG_NAME:=python3-paramiko
PKG_VERSION:=2.6.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://github.com/paramiko/paramiko/archive
PKG_MD5SUM:=161c71e27076eb1f2fc2fb2705d95a45

PKG_BUILD_DIR:=$(BUILD_DIR)/paramiko-$(PKG_VERSION)
PKG_BUILD_DEPENDS:=python3

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

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
endef

define Package/python3-paramiko/description
 Native Python SSHv2 protocol library 
endef

define Build/Compile
  $(call Build/Compile/PyMod,., \
      install --prefix="/usr" --root="$(PKG_INSTALL_DIR)" \
  )
endef

define Package/python3-paramiko/install
  $(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
  $(CP) \
    $(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
    $(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call Py3Package,python3-paramiko))
$(eval $(call BuildPackage,python3-paramiko))