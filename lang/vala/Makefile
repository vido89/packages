#
# Copyright (C) 2006-2017 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=vala
PKG_VERSION:=0.48.2
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=@GNOME/vala/0.48
PKG_HASH:=f095b0e624b8f4e5a426028ac255e477fad8c3b4c8cbbdebda8d6cd95bf79477

PKG_MAINTAINER:=
PKG_LICENSE:=LGPL-2.1-or-later
PKG_LICENSE_FILES:=COPYING

HOST_BUILD_DEPENDS:=glib2/host
HOST_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/host-build.mk

define Package/vala
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=C-sharp like language for the GObject system
  URL:=https://wiki.gnome.org/Projects/Vala
  BUILDONLY:=1
endef

define Package/vala/description
  Vala is a C-sharp like language for the GObject system. This package contains
  the Vala-to-C compiler for host.
endef

HOST_CONFIGURE_ARGS += \
	--disable-coverage \
	--disable-debug \
	--disable-valadoc \
	--without-cgraph

HOST_LDFLAGS += \
	-Wl,--rpath-link=$(STAGING_DIR_HOSTPKG)/lib

$(eval $(call HostBuild))
$(eval $(call BuildPackage,vala))
