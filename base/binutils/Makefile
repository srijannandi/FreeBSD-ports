# $FreeBSD$

PORTEPOCH=	0
CATEGORIES=	base
PKGNAMEPREFIX=	${OPSYS:tl}-
VALID_CATEGORIES=	base

COMMENT=	GNU binary tools for base

MASTERDIR=	${.CURDIR}/../../devel/binutils
PLIST=		${.CURDIR}/pkg-plist.${TARGET_ARCH}

.if !defined(CROSS_TOOLCHAIN)
.error Please define CROSS_TOOLCHAIN before building
.endif

.if !defined(CROSS_SYSROOT)
.error Please define CROSS_SYSROOT before building
.endif

TARGET_ARCH=	${CROSS_TOOLCHAIN:C,-.*$,,}
BUTARGET=	${TARGET_ARCH}-unknown-${OPSYS:tl}${OSREL}

CONFIGURE_ARGS+=	--disable-host-shared
PREFIX=	/usr

.include "${MASTERDIR}/Makefile"
