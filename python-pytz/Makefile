include $(TOPDIR)/rules.mk

PKG_NAME:=pytz
PKG_VERSION:=2015.4
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/source/p/pytz/
PKG_MD5SUM:=417a47b1c432d90333e42084a605d3d8
PKG_BUILD_DIR:=$(BUILD_DIR)/pytz-$(PKG_VERSION)
PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-pytz
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=python-pytz
  URL:=https://pypi.python.org/pypi/pytz
  DEPENDS:=+python
endef

define Package/pytz/description
   World timezone definitions, modern and historical
endef

define Build/Compile
	$(call Build/Compile/PyMod,., \
		install --prefix="/usr" --root="$(PKG_INSTALL_DIR)" \
	)
endef

define Package/python-pytz/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,python-pytz))
