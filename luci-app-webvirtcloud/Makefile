

include $(TOPDIR)/rules.mk


LUCI_TITLE:=LuCI support for webvirtcloud
LUCI_PKGARCH:=all
LUCI_DEPENDS:=+lsblk +docker +luci-lib-taskd +vmease

define Package/luci-app-webvirtcloud/conffiles
/etc/config/webvirtcloud
endef

define Package/luci-app-webvirtcloud/prerm
#!/bin/sh
/usr/libexec/istorec/webvirtcloud.sh stop
exit 0
endef

include $(TOPDIR)/feeds/luci/luci.mk

# call BuildPackage - OpenWrt buildroot signature
