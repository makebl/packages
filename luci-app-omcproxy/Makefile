# Copyright 2019 Shun Li <riverscn@gmail.com>
# This is free software, licensed under the Apache License, Version 2.0

include $(TOPDIR)/rules.mk

PKG_NAME:=luci-app-omcproxy

PKG_MAINTAINER:=Shun Li <riverscn@gmail.com>
PKG_LICENSE:=Apache-2.0

LUCI_TITLE:=LuCI support for omcproxy
LUCI_DEPENDS:=+omcproxy
LUCI_PKGARCH:=all

include $(TOPDIR)/feeds/luci/luci.mk

# call BuildPackage - OpenWrt buildroot signature
