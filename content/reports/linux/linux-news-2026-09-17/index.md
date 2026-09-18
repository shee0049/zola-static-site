+++
title = "Today's Linux News (September 17, 2026)"
description = "A roundup of the latest Linux and open-source news from the week of September 14–17, 2026."
date = 2026-09-17
template = "report.html"

[extra]
topic = "linux"
+++

# Today's Linux News (September 17, 2026)

**Topic:** Linux News
**Report generated:** 2026-09-17T20:57 (local) / 2026-09-18T00:57Z (UTC)

---

## Executive Summary

The second full week of September 2026 was a busy one for Linux and the broader open-source community. The headline event is the **Fedora Linux 45 Beta**, which ships the Linux 7.2 kernel alongside the forthcoming **GNOME 51** desktop and KDE Plasma 6.7. **Mozilla Firefox 156** landed with a substantially faster built-in PDF viewer as the browser settles into a two-week release cadence. Around the ecosystem, **KDE Plasma 6.8** entered public beta (final due in October), **COSMIC 1.8** reached general availability, **Debian 13.7** and **Ubuntu 24.04.5 LTS** pushed out maintenance releases, and several hardware/platform milestones (Asahi Linux on Apple M3, NVIDIA's open Linux driver) continued to mature.

---

## 1. Fedora Linux 45 Beta Released (Linux 7.2, GNOME 51, KDE Plasma 6.7)

The Fedora Project shipped the **Fedora Linux 45 Beta** this week for public testing. Final release is expected in **late October or early November 2026**.

- Powered by the latest **Linux 7.2 kernel series**.
- Flagship **Fedora Workstation** edition ships the soon-to-be-released **GNOME 51**.
- The **Fedora KDE Plasma** edition carries **Plasma 6.7**.

Notable changes in Fedora 45:

- **Fully reproducible package builds**.
- **kmscon** becomes the default virtual-terminal console.
- RPM signature checking is on by default (default package verification mode).
- Disk images for Fedora Atomic desktops are now built with the **image-builder** tool.
- A new **WebUI installer** on all Fedora Atomic ISO images, plus **web-based remote installation** for Atomic desktops.
- **systemd-oomd and zram swap by default** on Fedora CoreOS.
- GRUB EFI support for confidential computing; PAM support in `chpasswd` and `newusers`; IPv6 support in NetworkManager.
- Repo configuration data relocating from `/etc` to `/usr`; default Secrets Service provider switching from KWallet/GNOME Keyring to **oo7**; `ptrace` restricted by default; vendor change disabled by default for DNF5.

**Caveat:** this is a pre-release, so it's for testing, not production.

---

## 2. Mozilla Firefox 156 (Two-Week Cadence Continues)

Mozilla released **Firefox 156** about two weeks after Firefox 155, as the project settles into a faster **two-week release cycle**.

- Built-in **PDF viewer starts up to 45% faster**.
- Reduced memory and CPU use when displaying **large JPEG images** scaled down to fit a page.
- Android improvements and multiple bug fixes across platforms.
- Available for Linux, macOS, and Windows.

---

## 3. KDE Plasma 6.8 Enters Public Beta

**Plasma 6.8** moved into **public beta testing** this week, with the final release slated for **October 14, 2026** — the window previously highlighted as the point where Plasma drops its X11 session.

- Continued KWin and Wayland bug-fix work landed in **Plasma 6.7.5**.
- **KDE Gear 26.08.1** and **KDE Frameworks 6.30** also shipped, with improvements to Baloo (file indexer), KWallet, System Monitor, KIO, and image support.
- KDE's new **Photos app** was proposed as a future replacement for Gwenview.

---

## 4. COSMIC 1.8 Desktop Officially Released

System76's Rust-based **COSMIC desktop reached 1.8**, now generally available.

- Improved **touchscreen support**.
- Part of the ongoing maturation of the from-scratch desktop (own compositor, not a GNOME/KDE fork).
- Ships as the flagship desktop on **Pop!_OS**.

---

## 5. Distro Maintenance Releases: Debian 13.7 and Ubuntu 24.04.5 LTS

Two important point releases arrived this week:

- **Debian 13.7 "Trixie"** — 107 security updates and 106 bug fixes, mirrored across all Debian flavors (GNOME, KDE Plasma, Xfce, Cinnamon, LXQt, MATE, LXDE, and more).
- **Ubuntu 24.04.5 LTS** — refresh with an updated **HWE (Hardware Enablement) stack**, bringing **Linux 7.0** and **Mesa 26.2** to the LTS line. Released across the full 24.04 family (Kubuntu, Xubuntu, Lubuntu, Ubuntu Budgie, Ubuntu Cinnamon, Ubuntu Unity, Ubuntu MATE, and others).

Other distro activity: **KaOS 2026.09** (with Noctalia 5.1, Linux kernel 7.1, Mesa 26.2, and the Dinit init system), **MocaccinoOS 26.09** (x86-64-v3 optimized builds), and **openSUSE's Agama 24 installer** with improved storage, networking, and AutoYaST support.

---

## 6. Linux Mint: New Native Apps and Upstream Tooling

- Linux Mint developers introduced new **EPUB reader** and **Calendar** apps.
- The **xApp project** is expanding — Mint's apps can now be downloaded and used independently of a Mint release.

---

## 7. Hardware & Drivers: Asahi on M3, NVIDIA Open Driver

- **Asahi Linux officially supports Apple M3 Macs**.
- **NVIDIA 615.71 Linux driver** adds **Proton support for NVIDIA Reflex** and improves support for Vulkan-native games.
- **Bottles** pushes Windows app support further on ARM64 Linux.

---

## 8. Other Notable Releases & Projects

- **OpenSSL 4.1** alpha introduces DTLS 1.3, IKEv2 KDF, and GREASE support.
- **Linux kernel 7.2.5** point release, alongside LTS updates **6.18.51** and **6.12.109** (plus later 7.2.6).
- **Jellyfin 12.0** media server — faster database, modern UI.
- **GIMP 3.2.6** with UX improvements and new rotation stylus dynamics input.
- **Shotwell 0.33** — GTK4 port of the GNOME image viewer.
- **PipeWire 1.6.9** with better resampling quality.
- **GStreamer 1.28.7** — security and playback fixes, OpenCV 5 support.
- New **Rust-based open-source CAD app** ("Open CAD Studio") for Linux.
- **DietPi 10.7** adds container support with network and ARMv8 VMs.

---

## 9. Community and Ecosystem

- **Omarchy** funding surged to **$18.5M** with a **$3M pledge from DigitalOcean**.
- Debian continues its generative-AI policy work (Project formalizes responsible use of generative AI).
- California's age attestation bill to **exclude Linux and all open-source OSes**.
- The Linux Foundation published its September 2026 newsletter with ecosystem highlights and upcoming events.

---

## Sources

- 9to5Linux — *Fedora Linux 45 Beta Released with Linux 7.2, GNOME 51, and KDE Plasma 6.7* (this week)
- 9to5Linux — *9to5Linux Weekly Roundup: September 13th, 2026*
- Linuxiac — *Mozilla Firefox 156 Released with Up to 45% Faster PDF Viewer*
- Linuxiac — *Linuxiac Weekly Wrap-Up: Week 37, 2026 (September 7–13)*
- Linuxiac — *Linux & Open Source News* (category)
- Linux Foundation — *September 2026 Newsletter*
- DesktopLinux/Desdelinux — *September 2026: This month's news coverage of the Linuxverse*

---

*Report compiled from publicly available web sources on 2026-09-17. Release dates and feature sets are as reported by the cited sources and may vary slightly by edition or region.*