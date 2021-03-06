# Created by: Carlos J Puga Medina <cpm@fbsd.es>
# $FreeBSD$

PORTNAME=	acme
PORTVERSION=	${ACME_VERSION}
PORTEPOCH=	1
CATEGORIES=	security python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	python@FreeBSD.org
COMMENT=	ACME protocol implementation in Python

LICENSE=	APACHE20
LICENSE_FILE=	${WRKSRC}/LICENSE.txt

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}cryptography>=0.8:security/py-cryptography@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}josepy>=1.0.0:security/py-josepy@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}openssl>=0.13:security/py-openssl@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pyrfc3339>0:devel/py-pyrfc3339@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pytz>0:devel/py-pytz@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}requests>=2.10:www/py-requests@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}requests-toolbelt>=0.3.0:www/py-requests-toolbelt@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}setuptools>=1.0:devel/py-setuptools@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}six>0:devel/py-six@${PY_FLAVOR}
TEST_DEPENDS=	${PYTHON_PKGNAMEPREFIX}mock>0:devel/py-mock@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}nose>0:devel/py-nose@${PY_FLAVOR}

USES=		python
USE_PYTHON=	autoplist distutils

NO_ARCH=	yes

do-test:
	@cd ${WRKSRC} && ${PYTHON_CMD} ${PYDISTUTILS_SETUP} test

.include "version.mk"
.include <bsd.port.mk>
