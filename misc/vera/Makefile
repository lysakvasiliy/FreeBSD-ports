# Created by: Dima Sivachenko	<dima@chg.ru>
# $FreeBSD$

PORTNAME=	vera
PORTVERSION=	1.22
PORTREVISION=	1
CATEGORIES=	misc
MASTER_SITES=	GNU

MAINTAINER=	demon@FreeBSD.org
COMMENT=	Virtual Entity of Relevant Acronyms

LICENSE=	GFDL

USES=		makeinfo

INFO=		vera

do-build:
	(cd ${WRKSRC} && makeinfo --force --no-split vera.texi)

do-install:
	${INSTALL_DATA} ${WRKSRC}/vera.info ${STAGEDIR}${PREFIX}/${INFO_PATH}

.include <bsd.port.mk>
