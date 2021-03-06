# Created by: Neil Booth
# $FreeBSD$

PORTNAME=	electrum
PORTVERSION=	3.3.2
CATEGORIES=	finance python
MASTER_SITES=	https://download.electrum.org/${PORTVERSION}/ \
		http://download.electrum.org/${PORTVERSION}/
DISTNAME=	Electrum-${PORTVERSION}

MAINTAINER=	ehaupt@FreeBSD.org
COMMENT=	Easy to use Bitcoin client

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENCE

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}aiohttp-socks>=0.2:net/py-aiohttp-socks@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}aiohttp>0:www/py-aiohttp@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}aiorpcX>0:devel/py-aiorpcX@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}dnspython>0:dns/py-dnspython@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}httplib2>=0:www/py-httplib2@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}jsonrpclib-pelix>0:devel/py-jsonrpclib-pelix@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pbkdf2>=1.3:security/py-pbkdf2@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}protobuf>=2.6.0:devel/py-protobuf@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pyaes>0:security/py-pyaes@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pysocks>=0:net/py-pysocks@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}qrcode>=5.1:textproc/py-qrcode@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}requests>=2.4.3:www/py-requests@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}secp256k1>0:math/py-secp256k1@${PY_FLAVOR}

CONFLICTS_INSTALL=	electrum2-*

USES=		desktop-file-utils pyqt:5 python:3.4+
USE_PYQT=	gui_run sip widgets
USE_PYTHON=	autoplist distutils optsuffix
PYDISTUTILS_PKGNAME=	Electrum
NO_ARCH=	yes
OPTIONS_SUB=	yes

OPTIONS_DEFINE=	LEDGER TREZOR
OPTIONS_DEFAULT=LEDGER TREZOR

LEDGER_DESC=	Enable LEDGER Bitcoin hardware wallet support
TREZOR_DESC=	Enable TREZOR Bitcoin hardware wallet support

LEDGER_RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}btchip-python>0:security/py-btchip-python@${PY_FLAVOR}
TREZOR_RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}trezor>0:security/py-trezor@${PY_FLAVOR}

LEDGER_PLIST_FILES=	"@sample etc/devd/ledger_wallet.conf.sample"
TREZOR_PLIST_FILES=	"@sample etc/devd/trezor_wallet.conf.sample"

LEDGER_SUB_FILES=	pkg-message-hwwallet
TREZOR_SUB_FILES=	pkg-message-hwwallet

post-install-LEDGER-on:
	${INSTALL_DATA} ${FILESDIR}/ledger_wallet.conf.sample \
		${STAGEDIR}${PREFIX}/etc/devd

post-install-TREZOR-on:
	${INSTALL_DATA} ${FILESDIR}/trezor_wallet.conf.sample \
		${STAGEDIR}${PREFIX}/etc/devd

.include <bsd.port.mk>
