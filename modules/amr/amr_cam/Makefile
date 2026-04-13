.PATH: ${.CURDIR}/../../../dev/amr

KMOD=	amr_cam
SRCS=	amr_cam.c device_if.h bus_if.h
SRCS+=	opt_cam.h opt_scsi.h

CFLAGS+= -I${.CURDIR}/../../..

.include <bsd.kmod.mk>
