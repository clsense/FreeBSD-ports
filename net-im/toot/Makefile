# $FreeBSD$

PORTNAME=	toot
DISTVERSION=	0.19.0
CATEGORIES=	net-im python
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	0mp@FreeBSD.org
COMMENT=	Interact with the Mastodon social network from the command line

LICENSE=	GPLv3
LICENSE_FILE=	${WRKSRC}/LICENSE

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}beautifulsoup>=4.5.0:www/py-beautifulsoup@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}requests>=2.13:www/py-requests@${PY_FLAVOR}
TEST_DEPENDS=	${PYTHON_PKGNAMEPREFIX}beautifulsoup>=4.5.0:www/py-beautifulsoup@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pytest-cov>=2.4.0:devel/py-pytest-cov@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pytest>=3.0.0:devel/py-pytest@${PY_FLAVOR}

USES=		python:3.3+
USE_PYTHON=	autoplist distutils

USE_GITHUB=	yes
GH_ACCOUNT=	ihabunek

NO_ARCH=	yes

OPTIONS_DEFINE=	DOCS

PORTDOCS=	CHANGELOG.md README.rst

MAKE_ENV=	PATH+=${STAGEDIR}${PREFIX}/bin
TEST_TARGET=	coverage

pre-test:
	@${REINPLACE_CMD} -e 's|py.test |py.test-${PYTHON_VER} |' ${WRKSRC}/Makefile

post-install-DOCS-on:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${WRKSRC}/CHANGELOG.md ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${WRKSRC}/README.rst ${STAGEDIR}${DOCSDIR}

.include <bsd.port.mk>
