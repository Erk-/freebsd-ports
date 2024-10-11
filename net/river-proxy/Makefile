PORTNAME=	river
DISTVERSIONPREFIX=v
DISTVERSION=	0.5.0
PORTREVISION=	1
CATEGORIES=	net security

MAINTAINER=	ports@erk.dev
COMMENT=	River reverse proxy application, based on the pingora library from Cloudflare.
WWW=		https://www.memorysafety.org/initiative/reverse-proxy/

LICENSE=	APACHE20
LICENSE_FILE=	${WRKSRC}/LICENSE-APACHE

USES=		cargo
USE_GITHUB=	yes
GH_ACCOUNT=	memorysafety

WRKSRC=		${WRKDIR}/river-${DISTVERSION}

USERS=		river
GROUPS=		river

CARGO_USE_GITHUB=	yes

.include <bsd.port.pre.mk>

post-patch:
	${REINPLACE_CMD} -e s,%%WRKDIR%%,${WRKDIR}, ${WRKSRC}/Cargo.toml

post-install:
	${MV} ${WRKSRC}/source/river/assets/test-config.kdl ${STAGEDIR}${ETCDIR}/river.kdl.sample

# post-install-DOCS-on:

.include <bsd.port.mk>
