# $NetBSD: Makefile,v 1.3 2020/02/17 11:41:48 adam Exp $

DISTNAME=	pyftpdlib-1.5.6
PKGNAME=	${PYPKGPREFIX}-${DISTNAME}
CATEGORIES=	net python
MASTER_SITES=	${MASTER_SITE_PYPI:=p/pyftpdlib/}

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	https://github.com/giampaolo/pyftpdlib
COMMENT=	Very fast asynchronous FTP server library
LICENSE=	mit

DEPENDS+=	${PYPKGPREFIX}-OpenSSL-[0-9]*:../../security/py-OpenSSL
TEST_DEPENDS+=	${PYPKGPREFIX}-mock-[0-9]*:../../devel/py-mock
TEST_DEPENDS+=	${PYPKGPREFIX}-psutil-[0-9]*:../../sysutils/py-psutil
TEST_DEPENDS+=	${PYPKGPREFIX}-pysendfile-[0-9]*:../../net/py-pysendfile

USE_LANGUAGES=	# none

post-install:
	cd ${DESTDIR}${PREFIX}/bin && \
	${MV} ftpbench ftpbench-${PYVERSSUFFIX} || ${TRUE}

.include "../../lang/python/egg.mk"
.include "../../mk/bsd.pkg.mk"
