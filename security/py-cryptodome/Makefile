# $NetBSD: Makefile,v 1.35 2021/02/24 01:11:34 gutteridge Exp $

DISTNAME=	pycryptodome-3.10.1
PKGNAME=	${PYPKGPREFIX}-${DISTNAME:S/^py//}
CATEGORIES=	security python
MASTER_SITES=	${MASTER_SITE_PYPI:=p/pycryptodome/}

MAINTAINER=	pkgsrc-users@NetBSD.org
HOMEPAGE=	https://www.pycryptodome.org/
COMMENT=	Cryptographic and hash functions for Python
LICENSE=	public-domain AND python-software-foundation

EXTRACT_USING=	bsdtar

# XXX is this needed?
CFLAGS.SunOS+=	-std=c99 -D_XOPEN_SOURCE=600

CHECK_PORTABILITY_SKIP=	appveyor/get_wheels.sh

.include "../../lang/python/egg.mk"

# Python 3 builds of this package get an extra "abi3" suffix added
.if ${PYVERSSUFFIX} != "2.7"
PLIST_SUBST+=	SOEXT="abi3.so"
.else
PLIST_SUBST+=	SOEXT="so"
.endif

BUILDLINK_API_DEPENDS.gmp+=	gmp>=5.0
.include "../../devel/gmp/buildlink3.mk"
.include "../../mk/bsd.pkg.mk"
