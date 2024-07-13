PORTNAME=	wingpanel
DISTVERSION=	3.0.5
CATEGORIES=	x11

MAINTAINER=	inucat@proton.me
COMMENT=	Unofficial port of wingpanel
WWW=		https://github.com/elementary/wingpanel

LICENSE=	GPLv3

BUILD_DEPENDS=	gln:sysutils/coreutils
LIB_DEPENDS=	\
		libgee-0.8.so:devel/libgee \
		libgranite.so:x11-toolkits/granite \
		libgala.so:x11-wm/gala \
		libmutter-10.so:x11-wm/mutter

USES=gettext-tools vala meson ninja gnome pkgconfig
MESON_ARGS=		--prefix=${PREFIX}
MESON_BUILD_DIR=	build
USE_LDCONFIG=	yes
USE_GNOME=		glib20 gtk30
USE_GITHUB=		yes
GH_ACCOUNT=		elementary

do-build:
	cd ${WRKSRC} && meson setup build
	cd ${WRKSRC}/build && ninja

do-stage:
	cd ${WRKSRC}/build && DESTDIR=${WRKSRC}/../stage ninja install

.include <bsd.port.mk>
