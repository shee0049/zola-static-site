+++
title = "Linux News Roundup (October 5, 2026)"
description = "Ubuntu 26.10 Beta lands with 100% Rust coreutils, OpenMandriva ROME 26.09 and systemd-free Nitrux 7.0 ship, Debian Trixie patches 1300+ kernel CVEs, and Zig 0.17, Phosh 0.58, and Pangolin 1.24 land."
date = 2026-10-05
template = "report.html"

[extra]
topic = "linux"
+++

# Linux News Roundup (October 5, 2026)

**Topic:** Linux News
**Report generated:** 2026-10-05

---

## Executive Summary

The week of September 28 – October 4, 2026 opened the final stretch toward the **Ubuntu 26.10 (Stonking Stingray)** release, with **Canonical shipping the beta** on a **Linux 7.3** kernel and **GNOME 51**, and completing the **100% Rust coreutils migration**. **OpenMandriva Lx 26.09 "ROME"** and **Nitrux 7.0** both made the rounds as major rolling and systemd-free releases, while the **Debian Project** delivered what may be its biggest-ever kernel security update, patching more than **1313 CVEs** in the Linux 6.12 LTS series. On the developer tooling front, **Zig 0.17** arrived with a heavily reworked ELF linker and build system, mobile Linux got a fresh **Phosh 0.58**, and the self-hosting space saw **Pangolin 1.24** introduce full-tunnel Exit Nodes. Below is a closer look at the week's headlines.

---

## 1. Ubuntu 26.10 Beta: Rust Coreutils and GNOME 51

**Canonical** released the beta of the upcoming **Ubuntu 26.10 (Stonking Stingray)** on October 1 for public testing and early adopters, ahead of a final release expected on **October 15**. The beta is powered by the upcoming **Linux 7.3** kernel series, the **Mesa 26.2** graphics stack, and the recently released **GNOME 51** desktop environment. Headline news this cycle is the **100% Rust coreutils migration** — the default core utilities now run entirely on the Rust-based **uutils** implementation.

Ubuntu 26.10 also promises a complete desktop experience on **RVA23-compliant hardware**, improved driver management and multimedia support via the **GStreamer 1.30** framework, a new onboarding experience for newcomers, a simplified installer, and AI-powered speech-to-text voice interaction. Under the hood it transitions from `dbus-daemon` to **dbus-broker**, adds Microsoft password and MFA authentication support, and integrates Ubuntu Certified hardware information into GNOME Settings. A Release Candidate is expected around **October 8**, and the release will be supported for nine months, until June 2027.

---

## 2. OpenMandriva Lx 26.09 "ROME"

**OpenMandriva Lx 26.09 ROME** was released on October 1 as the rolling-release edition of the successor to the Mandriva Linux distribution. It is powered by the **Linux 7.2** kernel and features the latest **KDE Plasma 6.7** desktop with the **KDE Gear 26.08.1** and **KDE Frameworks 6.29** suites, alongside GNOME 50.3, Xfce 4.20, LXQt 2.4, MATE 1.28, Spectrwm, Hyprland 0.56.2, COSMIC 1.7, and Sway 1.12.

The release notably adds support for Canonical's **Snap** format alongside Flatpak and AppImage, and swaps **Ungoogled-Chromium for Helium** as the default browser on the KDE Plasma and LXQt editions. Under the hood, the toolchain is updated to LLVM/Clang 23, GCC 16.2, RPM 6.1, Qt 6.11.2, GTK 4.22.5, and ROCm 10.0.0, with almost all packages built with LTO enabled. New bootstrapping support heads to **RISC-V and LoongArch64**, the open NVIDIA kernel module has moved directly into the kernel, and gaming improves with the latest Steam Client, Proton, and DXVK. The COSMIC ISO was not published at release time due to a login-manager issue.

---

## 3. Systemd-Free Nitrux 7.0

The **Nitrux** team shipped **version 7.0** on October 1, coming more than four months after Nitrux 6.1. This immutable, **systemd-free** GNU/Linux distribution now runs the **Linux 7.2.6** kernel (with CachyOS patches) and the **Hyprland 0.55.4** Wayland compositor, with the Lüv 0.8.9 icon theme, KDE Frameworks 6.26, and MauiKit 4.0.4.

Nitrux 7.0 updates the **Nitrux Update Tool System** to 3.0.3 with a revamped updater interface, and the Calamares installer now uses **LUKS2** for encrypted partitions with Argon2id key derivation. New components include MauiKit System, a Nitrux KStyle widget style based on KDE's Breeze, the Toma screenshot/recording utility, and Hyprscreend for managing monitor modes, scaling, and external display hotplugging. Newer additions include Desklock (a native QML Wayland session locker), Valenz and Marina workspace shells, a Nitrux PolicyKit Agent, and the Nitrux Workspace Session Manager (nwsm).

---

## 4. Security: Debian's 1300+ CVE Kernel Update and Parrot OS 7.4

**Debian** released a kernel security update for **Debian 13 "Trixie"** on September 29 addressing **1313 security vulnerabilities** in the Linux 6.12 LTS series — likely the biggest kernel security release the project has ever shipped. Users are urged to update to **linux 6.12.111-1**. As the advisory explains, the bulk of these CVEs stems from two factors: a recent policy change that assigns a CVE to essentially any commit fixing a potential security issue, and Debian Stable's habit of accumulating fixes across multiple upstream point releases into large periodic batches. While the count sounds overwhelming, the vast majority are low-severity, highly conditional, or irrelevant to any given machine.

**ParrotSec** released **Parrot OS 7.4** on October 3, the fourth update in the Parrot OS 7.0 series (the first to default to KDE Plasma instead of MATE). Powered by the Linux 7.1 kernel on the Debian 13.6 base, it introduces **optimized ISOs for modern CPUs** — x86-64-v3 images for post-2015 x64 machines and armv8.2 builds benefiting Raspberry Pi 5, Apple Silicon M-series, and Cortex-X1 boards. Updated tools include **AnonSurf 6.0.1**, Rocket 2.0, Metasploit Framework 6.5.4, and several others, plus a refreshed Parrot Updater 2.2.0.

---

## 5. Developer Tooling: Zig 0.17

**Zig 0.17** was released, advancing the systems programming language with major improvements to its new **ELF linker**, which now has full x86_64 and SPARC64 support and partial LoongArch. It can generate static and shared libraries, handle GNU symbol versioning, DWARF debug info, and GOT generation, and developers say it can already build most x86_64 Linux projects — though it is not yet the default, with retirement of the legacy linker planned next release. **Incremental compilation** is significantly improved, working with Zig's watch mode for near-immediate rebuilds.

The build system now runs its configuration and build-graph stages as separate processes, with a binary cache about 25% smaller and cache hits 5–10% faster. A new **Build Server Protocol** gives IDEs access to the build graph, though it temporarily breaks some ZLS (Zig Language Server) functionality. Platform support adds loongarch32-linux targets, generally usable 64-bit SPARC, and early xtensa-linux support, while the toolchain upgrades to **LLVM/Clang 22.1.8** and glibc 2.44 for cross-compilation.

---

## 6. Mobile Linux: Phosh 0.58

**Phosh**, the GNOME-based Linux mobile shell, reached **version 0.58** with a more convenient screenshot workflow — users can now open a captured image or its folder directly from the notification. The Caffeine quick setting is more configurable, and startup tracking for Flatpak apps and D-Bus-owning applications improved. On the compositor side, **Phoc 0.58** adds basic text-input-v3 support for GTK 4.24 compatibility, layer-shell-effects v4, and a fix for a fling-gesture crash. The **Stevia** on-screen keyboard now allows completion dictionaries to be installed in the user's home directory — useful for immutable systems — and Phosh First Boot 0.2 adds configurable username/password minimums, auto-adds users to `sudo`, and defaults to systemd-homed's LUKS backend. Device support through gmobile 0.7.4 adds the Google Pixel 3 XL display and Pixel 9a.

---

## 7. Self-Hosting: Pangolin 1.24

**Pangolin 1.24**, the open-source tunneled reverse proxy and zero-trust platform built around WireGuard, added **Exit Nodes** as its headline feature. Where Pangolin previously acted as a split-tunnel solution, users can now create a private resource as an Exit Node; once a client selects it, all internet traffic routes through the associated site — giving full-tunnel VPN capability. With multiple sites, Pangolin auto-selects by latency, throughput, and availability, supporting TCP, UDP, and ICMP. A notably Linux-focused addition is **Subnet Router** support, letting a single Linux client advertise an entire subnet so other devices reach Pangolin resources without installing the client. Client updates roll out across Windows, macOS, iOS, Android, and the CLI.

---

## 8. Other Releases & Ecosystem

The week's broader ecosystem (per the 9to5Linux weekly roundup and Linuxiac Week 40 wrap-up) included **Firefox 157 Nova** with a major visual refresh, **LibreOffice 26.8.1** with 40+ fixes, **Mozilla Thunderbird 157**, **Arch Linux's October 2026 ISO** with the ArchInstall 4.5 installer, and **antiX Linux 26.1** as a Debian-based systemd-free release. Software saw versions of **Git 2.56**, **Wine 11.19**, **Flatpak 1.18.4**, **OpenSSL 4.0.3**, **Rust 1.99**, **Qt 6.12 LTS**, **Darktable 5.6.2**, and video editors **Shotcut 26.9** and **OpenShot 4.0.1**. Notable community items included **Rust becoming a Tier-1 language at Microsoft**, COSMIC stopping acceptance of LLM-generated pull-request content, Ubuntu 24.04 LTS users now able to upgrade to 26.04.1 LTS, and **KDE Plasma 6.8** due on **October 14**. Kernel point releases arrived across the 7.2, 6.18, 6.12, 6.6, 6.1, 5.15, and 5.10 LTS lines. Looking ahead, Ubuntu 26.10 final and KDE Plasma 6.8 both land mid-October.

---

## Sources

- 9to5Linux — *9to5Linux Weekly Roundup: October 4th, 2026* (October 4, 2026) — https://9to5linux.com/9to5linux-weekly-roundup-october-4th-2026
- Linuxiac — *Linuxiac Weekly Wrap-Up: Week 40, 2026 (September 28 – October 4)* (October 4, 2026) — https://linuxiac.com/linuxiac-weekly-wrap-up-week-40-2026-september-28-october-4/
- 9to5Linux — *Ubuntu 26.10 Beta Released with Linux Kernel 7.3 and GNOME 51* (October 1, 2026) — https://9to5linux.com/ubuntu-26-10-beta-released-with-linux-kernel-7-3-and-gnome-51
- 9to5Linux — *OpenMandriva Lx 26.09 "ROME" Released with KDE Plasma 6.7 and Linux Kernel 7.2* (October 1, 2026) — https://9to5linux.com/openmandriva-lx-26-09-rome-released-with-kde-plasma-6-7-and-linux-kernel-7-2
- 9to5Linux — *Systemd-Free Nitrux 7.0 Released with Linux Kernel 7.2 and Hyprland 0.55.4* (October 1, 2026) — https://9to5linux.com/systemd-free-nitrux-7-0-released-with-linux-kernel-7-2-and-hyprland-0-55-4
- 9to5Linux — *Latest Debian 13 "Trixie" Kernel Security Update Patches More Than 1300 CVEs* (October 2, 2026) — https://9to5linux.com/latest-debian-13-trixie-kernel-security-update-patches-more-than-1300-cves
- 9to5Linux — *Parrot OS 7.4 Released with AnonSurf 6.0, Updated Raspberry Pi Images* (October 3, 2026) — https://9to5linux.com/parrot-os-7-4-released-with-anonsurf-6-0-updated-raspberry-pi-images
- Linuxiac — *Zig 0.17 Programming Language Lands With Reworked Build System* (October 4, 2026) — https://linuxiac.com/zig-0-17-programming-language-lands-with-reworked-build-system/
- Linuxiac — *Phosh 0.58 Linux Mobile Shell Improves Screenshots and Flatpak Apps* (October 5, 2026) — https://linuxiac.com/phosh-0-58-linux-mobile-shell-improves-screenshots-and-flatpak-apps/
- Linuxiac — *Pangolin 1.24 Tunneled Reverse Proxy Adds Exit Nodes, Linux Subnet Routing* (October 4, 2026) — https://linuxiac.com/pangolin-1-24-tunneled-reverse-proxy-adds-exit-nodes-linux-subnet-routing/

---

*Report compiled from publicly available web sources on 2026-10-05. Release dates, versions, and figures are as reported by the cited sources and may vary slightly by edition or region.*