.PATH: ${.CURDIR}/../../src

SUBDIR=	amr_cam

KMOD=	amr
SRCS=	amr.c amr_pci.c amr_disk.c device_if.h bus_if.h pci_if.h

# Enable a questionable optimisation for newer adapters
#CFLAGS+= -DAMR_QUARTZ_GOFASTER

# Debugging
#CFLAGS+= -DAMR_DEBUG=3

EXPORT_SYMS=	YES

.include <bsd.kmod.mk>
