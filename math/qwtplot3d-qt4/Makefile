# $FreeBSD$

PORTNAME=	qwtplot3d
PORTVERSION=	0.2.7
PORTREVISION=	6
CATEGORIES=	math
MASTER_SITES=	SF
PKGNAMESUFFIX=	-qt4

MAINTAINER=	ports@FreeBSD.org
COMMENT=	3D plotting widgets for scientific data and math expressions

DEPRECATED=		Qt4 has been EOL since december 2015
EXPIRATION_DATE=	2019-03-15

USES=		dos2unix qmake qt:4 tar:tgz
USE_QT=		gui moc_build opengl
USE_GL=		glu
USE_LDCONFIG=	yes

WRKSRC=	${WRKDIR}/${PORTNAME}

do-install:
	@${MKDIR} ${STAGEDIR}${PREFIX}/include/qwtplot3d-qt4
	${INSTALL_DATA} ${WRKSRC}/include/*.h ${STAGEDIR}${PREFIX}/include/qwtplot3d-qt4
	${INSTALL_LIB} ${WRKSRC}/lib/libqwtplot3d-qt4.so.${PORTVERSION} ${STAGEDIR}${PREFIX}/lib
	${LN} -fs libqwtplot3d-qt4.so.${PORTVERSION} ${STAGEDIR}${PREFIX}/lib/libqwtplot3d-qt4.so.0
	${LN} -fs libqwtplot3d-qt4.so.${PORTVERSION} ${STAGEDIR}${PREFIX}/lib/libqwtplot3d-qt4.so

.include <bsd.port.mk>
