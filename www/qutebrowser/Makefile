# $FreeBSD$

PORTNAME=	qutebrowser
DISTVERSION=	1.2.1
CATEGORIES=	www
MASTER_SITES=	CHEESESHOP

MAINTAINER=	novel@FreeBSD.org
COMMENT=	Keyboard-focused browser with a minimal GUI

LICENSE=	GPLv3

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}attrs>=0:devel/py-attrs@${FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}colorama>=0:devel/py-colorama@${FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}cssutils>=0:www/py-cssutils@${FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}Jinja2>=0:devel/py-Jinja2@${FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}MarkupSafe>=0:textproc/py-MarkupSafe@${FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pygments>=0:textproc/py-pygments@${FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pyPEG2>=0:textproc/py-pyPEG2@${FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}yaml>0:devel/py-yaml@${FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}sip>=0:devel/py-sip@${FLAVOR} \
		${LOCALBASE}/lib/alsa-lib/libasound_module_pcm_oss.so:audio/alsa-plugins

USES=		desktop-file-utils python:3.5+ pyqt:5
USE_PYQT=	core opengl printsupport sql widgets qml
USE_QT5=	sql-sqlite3
USE_PYTHON=	distutils autoplist

NO_ARCH=	yes
PLIST_FILES=	share/applications/${PORTNAME}-${PYTHON_VER}.desktop

OPTIONS_MULTI=	BACKEND
OPTIONS_MULTI_BACKEND=	WEBKIT WEBENGINE
OPTIONS_DEFAULT=	WEBKIT WEBENGINE

WEBENGINE_DESC=		WebEngine webpage renderer support

WEBKIT_USE=	PYQT=webkit,webkitwidgets
WEBENGINE_USE=	PYQT=webengine,webchannel

post-install:
	${INSTALL_DATA} ${WRKSRC}/misc/${PORTNAME}.desktop \
		${STAGEDIR}${PREFIX}/share/applications/${PORTNAME}-${PYTHON_VER}.desktop

.include <bsd.port.mk>
