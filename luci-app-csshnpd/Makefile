include $(TOPDIR)/rules.mk

PKG_NAME:=luci-app-csshnpd
PKG_LICENSE:=GPL-2.0
PKG_MAINTAINER:=Chris Swan <chris@atsign.com>

LUCI_TITLE:=NoPorts Web UI
LUCI_DESCRIPTION:=LuCI config app for NoPorts daemon (csshnpd)
LUCI_DEPENDS:=+luci-base +csshnpd
LUCI_PKGARCH:=all

include $(TOPDIR)/feeds/luci/luci.mk

# call BuildPackage - OpenWrt buildroot signature
