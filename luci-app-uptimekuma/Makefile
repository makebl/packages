

include $(TOPDIR)/rules.mk


LUCI_TITLE:=LuCI support for UptimeKuma
LUCI_PKGARCH:=all
LUCI_DEPENDS:=+lsblk +zoneinfo-asia +docker +luci-lib-taskd +luci-lib-docker

define Package/luci-app-uptimekuma/conffiles
/etc/config/uptimekuma
endef

define Package/luci-app-uptimekuma/prerm
#!/bin/sh
/usr/libexec/istorec/uptimekuma.sh stop
exit 0
endef

include $(TOPDIR)/feeds/luci/luci.mk

# call BuildPackage - OpenWrt buildroot signature
