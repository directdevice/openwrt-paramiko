include $(TOPDIR)/rules.mk

PKG_NAME:=python3-bcrypt
PKG_VERSION:=3.1.7
PKG_RELEASE:=1

PKG_SOURCE:=bcrypt-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:= https://files.pythonhosted.org/packages/source/b/bcrypt
PKG_HASH:=0b0069c752ec14172c5f78208f1863d7ad6755a6fae6fe76ec2c80d13be41e42

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_BUILD_DEPENDS:=libffi/host

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python3-bcrypt
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=python3-bcrypt
  URL:=https://github.com/pyca/bcrypt
  DEPENDS:= \
    +PACKAGE_python3-bcrypt:python3 \
    +PACKAGE_python3-bcrypt:python3-cffi \
    +PACKAGE_python3-bcrypt:python3-six
  VARIANT:=python3
endef

define Package/python3-bcrypt/description
  Modern password hashing
endef

$(eval $(call Py3Package,$(PKG_NAME)))
$(eval $(call BuildPackage,$(PKG_NAME)))