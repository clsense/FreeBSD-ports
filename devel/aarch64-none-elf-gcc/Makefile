# $FreeBSD$

PKGNAMEPREFIX=	aarch64-none-elf-
COMMENT=	GNU Compiler Collection for bare metal arm cross-development
GCC_TARGET=	aarch64-none-elf
PLIST=	${.CURDIR}/pkg-plist

# U-Boot requires libgcc, crossbuild and install it along with the compiler.
ALL_TARGET=	all-gcc all-target-libgcc
INSTALL_TARGET=	install-gcc install-target-libgcc

BROKEN_mips=		configure: error: cannot compute suffix of object files: cannot compile
BROKEN_mips64=		configure: error: cannot compute suffix of object files: cannot compile
BROKEN_powerpc64=	fails to compile: libgcc2.c:1846:9: internal compiler error: Segmentation fault

MASTERDIR=	${.CURDIR}/../powerpc64-gcc

.include "${MASTERDIR}/Makefile"

# The following is required for clang to bootstrap gcc.
.if ${COMPILER_TYPE} == clang
MAKE_ARGS+=	CXXFLAGS=-fbracket-depth=512
.endif
