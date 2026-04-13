# freebsd-amr-kmod

FreeBSD kernel module for the amr(4) MegaRAID SCSI/ATA/SATA RAID controller driver.

This driver was removed from the FreeBSD kernel in
[commit 60de2867c9fc](https://cgit.freebsd.org/src/commit/?id=60de2867c9fc)
(November 2021, before FreeBSD 14.0). This repository preserves the driver
source so it can be built as a loadable kernel module (kmod) for FreeBSD 14.x
and later.

## Supported Hardware

LSI Logic / American Megatrends MegaRAID controllers, including those found
in Dell PowerEdge servers (e.g., PowerEdge 1850).

See the [amr(4) man page](man/amr.4) for a full list of supported controllers.

## Building

### From the FreeBSD port

```sh
cd /usr/ports/sysutils/amr-kmod
make install clean
```

Or install the binary package:

```sh
pkg install amr-kmod
```

### Manual build

Requires FreeBSD kernel source headers in `/usr/src/sys`.

```sh
cd modules/amr
make
make install
```

## Loading

Add to `/boot/loader.conf`:

```
amr_load="YES"
amr_cam_load="YES"
```

Or load manually:

```sh
kldload amr
kldload amr_cam
```

## Modules

- **amr.ko** — Core MegaRAID driver (PCI attachment, disk interface)
- **amr_cam.ko** — CAM (Common Access Method) interface for SCSI passthrough

## License

BSD-2-Clause AND BSD-3-Clause (see source file headers for details).

## Origin

Source extracted from FreeBSD src at commit
[399188a2c60c](https://cgit.freebsd.org/src/commit/?id=399188a2c60caffe496d03f8ddd6c1b1c34dc3ed)
(the last revision containing the amr driver).
