+++
title = "Linux News Roundup (September 18, 2026)"
description = "GNOME 51 lands, Ubuntu 26.10 reaches its final snapshot, Firefox 157 previews the Nova design, and more from the week of September 14–18, 2026."
date = 2026-09-18
template = "report.html"

[extra]
topic = "linux"
+++

# Linux News Roundup (September 18, 2026)

**Topic:** Linux News
**Report generated:** 2026-09-18T18:00 (local) / 2026-09-18T23:00Z (UTC)

---

## Executive Summary

The week of September 14–18, 2026 was headlined by the official release of **GNOME 51 “A Coruña”**, the first major GNOME desktop release since 2.34 and a showcase feature of the Fedora 45 Beta that also landed this week. **Ubuntu 26.10 “Stonking Stingray”** shipped its fourth and final development snapshot ahead of an October 15 final, and Mozilla previewed a brand-new **“Nova” design** in the Firefox 157 beta. Elsewhere, **Raspberry Pi OS** gained dock support, NVIDIA introduced a native Rust path for CUDA GPU kernels, **Wine 11.18** and **MariaDB 13.0** shipped, and **The Document Foundation** set a first-week download record while firmly declaring that “no AI is a feature.”

---

## 1. GNOME 51 “A Coruña” Officially Released

The GNOME Project released **GNOME 51** on September 16 as the latest stable desktop environment. Notable highlights include:

- **Monitor brightness** can now be saved and restored.
- Support for **elogind** as a libsystemd provider and a new **QR-code generation API** (exposed via the input capture portal with clipboard integration).
- Initial support for the **“reduced-motion”** accessibility setting, web login with a unified auth mechanism, and SVG-based cursor implementations.
- Support for the **ext-background-effect-v1 blur Wayland protocol** and external cursor implementations.
- **Nautilus (Files) 51** adds a count badge when dragging multiple files and faster view reloading.
- **Control Center (Settings) 51** gains Auto Rotate for accelerometer-equipped devices, DNS search in Network, fingerprint management in Users, and a removal of legacy WEP support.
- **GNOME Remote Desktop 51** enables hardware acceleration for AMD GPUs via the AMDGPU driver; **GNOME Session 51** now uses oo7-portal for the Secret portal.
- GDM 51 adds settings for fallback session selection and headless-only systems.

The project has already set the next milestone: **GNOME 52 “Terengganu”** is planned for March 2027.

---

## 2. Fedora 45 Beta with GNOME 51

Fedora Linux **45 Beta** became available for public testing on September 15. It ships the **Linux 7.2 kernel**, the flagship Workstation edition featuring GNOME 51, and a KDE Plasma edition carrying Plasma 6.7. Beyond new desktops, Fedora 45 emphasizes fully reproducible package builds, kmscon as the default virtual-terminal console, RPM signature checking on by default, and a new WebUI installer for Fedora Atomic images. The final release is expected in late October or early November; this is a pre-release build intended for testing.

---

## 3. Ubuntu 26.10 “Stonking Stingray” Final Snapshot

Canonical released **Ubuntu 26.10 Snapshot 4** on September 17 — the fourth and final development milestone for the Stonking Stingray cycle, running the **Linux 7.2 kernel**. It previews several incoming features, including a new onboarding experience, on-device speech-to-text voice interaction, a package-agnostic App Center, and an improved driver-management experience. The **beta is expected on September 24**, and the **final release on October 15, 2026**, powered by Linux 7.3, Mesa 26.2, and the GNOME 51 desktop series. As with all snapshots, the images are for early adopters and developers, not production.

---

## 4. Mozilla: Firefox 156 Formal + Firefox 157 Beta “Nova”

Mozilla released **Firefox 156** earlier in the week (faster PDF viewer, reduced memory/CPU use for large JPEGs), and on September 15 unveiled **Firefox 157**, now in public beta, carrying a brand-new theme called **Nova**.

- Nova aims for a cleaner, faster, more adaptable interface, and restores a **Compact** spacing mode alongside Standard and Touch modes.
- Firefox 157 properly displays **HDR videos encoded in 8-bit color formats** as HDR, fixing dull, gray-looking videos.
- Improved **audio/video synchronization** on playback rate changes and a better-behaved **Vertical Tabs sidebar** in full-screen mode.

Meanwhile, **Mozilla Thunderbird 156** (September 15) added custom OAuth support for POP3 along with assorted fixes.

---

## 5. Raspberry Pi OS Brings Dock Support

The Raspberry Pi Foundation published **Raspberry Pi OS 2026-09-15**, based on Debian 13 “Trixie” and powered by the Linux **6.18.50 LTS** kernel. The release adds **dock support** to the Wayland panel (wf-panel-pi) with new Icon Menu and Icon Tasklist plugins, plus a **new screenshot tool**, a monolithic PCManFM/libfm build, switchable Ejecter automounting, and support for **labwc 0.20 / wlroots**. It is available for all supported Pi models including Zero, Zero 2 W, and 400.

---

## 6. Tooling & Open-Source Software

- **NVIDIA introduces CUDA Rust** (September 18): two tracks — `cuda-oxide` (SIMT model with a custom rustc code-generation backend through MIR → Pliron → LLVM IR → PTX) and `cutile-rs` (CUDA Tile model using tensor partitioning and Rust ownership for compile-time race rejection). Interop with CUDA C++/Python is planned.
- **Wine 11.18** (September 18): expanded NTOSKRNL support for kernel drivers and C header compatibility fixes, 21 bug fixes including Assassin’s Creed Rogue, Super Meat Boy, and Star Wars: KOTOR, plus ARM64EC and Adobe Creative Cloud fixes.
- **MariaDB 13.0** goes stable (September 18) with new SQL and InnoDB features.
- **Java 27** (September 18) ships with G1 as the default garbage collector, Compact Object Headers, and TLS improvements.
- **VirtualBox 7.2.18** (September 15): Linux 7.3 compilation fixes and RHEL 10.3 kernel support.
- **DXVK 3.1.1** (September 15): fixes for Call of Duty: Ghosts, Rayman 3, and Skyrim SE.
- **PipeWire 1.6.9** (September 17): improved Bluetooth, JACK, ALSA plugin, and Pulse server handling.
- **Rust Coreutils 0.12** improves Ubuntu compatibility and GNU parity; **Mojo 1.1** opens its compiler to external contributions; **Miracle WM 0.11** (Wayland compositor) adds a new workspace overview mode.

---

## 7. LibreOffice 26.8 Download Record + “No AI” Stance

On September 18, The Document Foundation revealed that **LibreOffice 26.8** was downloaded **1,031,162 times from the official page in its first week** (excluding Linux distro repository installs), a record. A day later TDF published a post titled *“Yes, no AI is now a feature,”* explaining that no current AI integration meets its standards for default deployment — open interfaces (no single-vendor lock-in), OpenDocument preservation, no telemetry, and fully optional install. TDF says LibreOffice will keep shipping without built-in AI for now, while third-party extensions (e.g., Ollama/LM Studio) remain available.

---

## 8. Other Distros & Ecosystem

- **Calibre 9.15** (September 18) adds an AI-assisted “Create Your Own Adventure” storytelling mode.
- **HPLIP 3.26.6** (September 17) adds support for newer HP printers.
- **Talos Enterprise Linux** launched for Kubernetes infrastructure, and **Calibre**, **PipeWire**, and **Mesa 26.2.3** are among the packaged updates in downstream distro repos this week.

---

## Sources

- 9to5Linux — *GNOME 51 “A Coruña” Desktop Environment Officially Released, This Is What’s New* (September 16, 2026) — https://9to5linux.com/gnome-51-a-coruna-desktop-environment-officially-released-this-is-whats-new
- 9to5Linux — *Fedora Linux 45 Beta Released with Linux 7.2, GNOME 51, and KDE Plasma 6.7* (September 15, 2026) — https://9to5linux.com/fedora-linux-45-beta-released-with-linux-7-2-gnome-51-and-kde-plasma-6-7
- 9to5Linux — *Ubuntu 26.10 “Stonking Stingray” Snapshot 4 Is Out for Public Testing with Linux 7.2* (September 17, 2026) — https://9to5linux.com/ubuntu-26-10-stonking-stingray-snapshot-4-is-out-for-public-testing-with-linux-7-2
- 9to5Linux — *Mozilla Firefox 157 Enters Public Beta Testing with Brand-New Nova Design* (September 15, 2026) — https://9to5linux.com/mozilla-firefox-157-enters-public-beta-testing-with-brand-new-nova-design
- 9to5Linux — *Latest Raspberry Pi OS Release Brings Dock Support and New Screenshot Tool* (September 15, 2026) — https://9to5linux.com/latest-raspberry-pi-os-release-brings-dock-support-and-new-screenshot-tool
- 9to5Linux — *Mozilla Thunderbird 156 Email Client Brings Custom OAuth Support for POP3* (September 15, 2026) — https://9to5linux.com/mozilla-thunderbird-156-email-client-brings-custom-oauth-support-for-pop3
- Linuxiac — *LibreOffice 26.8 Sets Download Record as TDF Says “No AI” Is a Feature* (September 18, 2026) — https://linuxiac.com/libreoffice-26-8-sets-download-record-as-tdf-says-no-ai-is-a-feature/
- Linuxiac — *NVIDIA Introduces CUDA Rust for Writing GPU Kernels* (September 18, 2026) — https://linuxiac.com/nvidia-introduces-cuda-rust-for-writing-gpu-kernels/
- Linuxiac — *Wine 11.18 Improves Windows Kernel Driver Support* (September 18, 2026) — https://linuxiac.com/wine-11-18-improves-windows-kernel-driver-support/
- Linuxiac — *MariaDB 13.0 Goes Stable with New SQL and InnoDB Features* (September 18, 2026) — https://linuxiac.com/mariadb-13-0-goes-stable-with-new-sql-and-innodb-features/
- Linuxiac — *Java 27 Released with G1 as the Default Garbage Collector* (September 18, 2026) — https://linuxiac.com/java-27-released-with-g1-as-the-default-garbage-collector/
- 9to5Linux news feed and home page, plus Linuxiac news category (accessed September 18, 2026)

---

*Report compiled from publicly available web sources on 2026-09-18. Release dates, versions, and figures are as reported by the cited sources and may vary slightly by edition or region.*