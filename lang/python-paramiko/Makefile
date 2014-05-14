include $(TOPDIR)/rules.mk

PKG_NAME:=python-paramiko
PKG_VERSION:=1.12.4
PKG_RELEASE:=1

PKG_SOURCE:=v$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://github.com/paramiko/paramiko/archive
PKG_MD5SUM:=407b1b7bfdc29e6ccb460afbc78f156d

PKG_BUILD_DIR:=$(BUILD_DIR)/paramiko-$(PKG_VERSION)
PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-paramiko
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=python-paramiko
  URL:=https://github.com/paramiko/paramiko
  DEPENDS:=+python
endef

define Package/paramiko/description
 Native Python SSHv2 protocol library 
endef

define Build/Compile
	$(call Build/Compile/PyMod,., \
		install --prefix="/usr" --root="$(PKG_INSTALL_DIR)" \
	)
endef

define Package/python-paramiko/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,python-paramiko))
