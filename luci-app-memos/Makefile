

include $(TOPDIR)/rules.mk


LUCI_TITLE:=LuCI support for Memos
LUCI_PKGARCH:=all
LUCI_DEPENDS:=+lsblk +docker +luci-lib-taskd

define Package/luci-app-memos/conffiles
/etc/config/memos
endef

include $(TOPDIR)/feeds/luci/luci.mk

# call BuildPackage - OpenWrt buildroot signature
