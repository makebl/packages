

include $(TOPDIR)/rules.mk


LUCI_TITLE:=LuCI support for 1Panel
LUCI_PKGARCH:=all
LUCI_DEPENDS:=+lsblk +zoneinfo-asia +docker +luci-lib-taskd +luci-lib-docker

define Package/luci-app-istorepanel/conffiles
/etc/config/istorepanel
endef

include $(TOPDIR)/feeds/luci/luci.mk

# call BuildPackage - OpenWrt buildroot signature
