include $(TOPDIR)/rules.mk

PKG_NAME:=python-paramiko
PKG_VERSION:=1.12.4
PKG_RELEASE:=1

PKG_SOURCE:=v$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://github.com/paramiko/paramiko/archive
PKG_MD5SUM:=407b1b7bfdc29e6ccb460afbc78f156d

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python-package.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python-paramiko
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=python-paramiko
  URL:=https://github.com/paramiko/paramiko
  DEPENDS:= \
    +PACKAGE_python-paramiko:+python \
    +PACKAGE_python-paramiko:+python-crypto
  VARIANT:=python
endef

define Package/python-paramiko/description
 Native Python SSHv2 protocol library
endef

$(eval $(call Py3Package,$(PKG_NAME)))
$(eval $(call BuildPackage,$(PKG_NAME)))
