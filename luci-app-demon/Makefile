

include $(TOPDIR)/rules.mk


LUCI_TITLE:=LuCI support for demon
LUCI_PKGARCH:=all
LUCI_DEPENDS:=+lsblk +docker +luci-lib-taskd

define Package/luci-app-demon/conffiles
/etc/config/demon
endef

# prerm
# postrm
define Package/luci-app-demon/prerm
#!/bin/sh
docker rm -f demon
exit 0
endef

include $(TOPDIR)/feeds/luci/luci.mk

# call BuildPackage - OpenWrt buildroot signature
