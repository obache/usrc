# $NetBSD: Makefile,v 1.2 2021/06/23 20:33:07 nia Exp $

.include "../../databases/lua-dbi/Makefile.common"

PKGNAME=	${LUA_PKGPREFIX}-${DISTNAME:S/^lua//1:S/dbi/dbi-postgresql/1}
PKGREVISION=	1

MAINTAINER=	pkgsrc-users@NetBSD.org
COMMENT=	Multi-backend SQL database library for Lua (mysql backend)

DEPENDS+=	${LUA_PKGPREFIX}-dbi-[0-9]*:../../databases/lua-dbi

BUILD_TARGET=	mysql

INSTALLATION_DIRS+=	${LUA_CDIR}/dbd

do-install:
	${INSTALL_LIB} ${WRKSRC}/dbd/mysql.so \
		${DESTDIR}${PREFIX}/${LUA_CDIR}/dbd

.include "../../mk/mysql.buildlink3.mk"
.include "../../mk/bsd.pkg.mk"
