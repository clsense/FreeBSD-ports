# $FreeBSD$

PORTNAME=	kjumpingcube
DISTVERSION=	${KDE_APPLICATIONS_VERSION}
CATEGORIES=	games kde kde-applications

MAINTAINER=	kde@FreeBSD.org
COMMENT=	${${PORTNAME}_DESC}

USES=		cmake:outsource gettext kde:5 qt:5 tar:xz
USE_KDE=	auth codecs completion config configwidgets coreaddons crash \
		dbusaddons ecm guiaddons i18n  iconthemes itemviews jobwidgets \
		kio libkdegames newstuff notifyconfig service widgetsaddons \
		xmlgui
USE_QT=		core dbus gui network qml quick svg widgets xml \
		buildtools_build qmake_build

OPTIONS_DEFINE=	DOCS

.include <${.CURDIR}/../kdegames/Makefile.common>
.include <bsd.port.mk>
