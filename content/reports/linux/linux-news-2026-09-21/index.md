+++
title = "Linux News Roundup (September 21, 2026)"
description = "MX Linux 25.3 “Infinity” ships, Garuda Linux launches Garuda Nix, Peppermint OS begins shifting from X.Org to XLibre, GNU Wget 2.3 and Kitty 0.49 land, and more from the week of September 14–21, 2026."
date = 2026-09-21
template = "report.html"

[extra]
topic = "linux"
+++

# Linux News Roundup (September 21, 2026)

**Topic:** Linux News
**Report generated:** 2026-09-21

---

## Executive Summary

The week of September 14–21, 2026 was heavy on **distribution releases** and **system-level tooling**. **MX Linux 25.3 “Infinity”** became the latest update in the popular Debian-based series, and **Garuda Linux** took an unusual step by launching **Garuda Nix**, a standalone NixOS-based flavor that charts a path away from its usual Arch foundation. **Peppermint OS** signaled a significant shift underway in the X11 ecosystem by starting to replace the X.Org Server with the **XLibre** implementation, while **GNU Wget 2.3** and **Kitty 0.49** delivered meaningful security and performance work. On the self-hosting front, **RustFS 1.0** reached general availability as an open-source S3-compatible object store, **Portainer 3.0** pivoted to a Kubernetes-first codebase, and **Pangolin 1.23** simplified clustered reverse-proxy deployments. Below is a closer look at the week’s headlines.

---

## 1. MX Linux 25.3 “Infinity”

The MX Linux team released **MX Linux 25.3** on September 20 as the third update in the MX Linux 25 “Infinity” series, available with Xfce, KDE Plasma, and Fluxbox flavors. Coming roughly four months after MX Linux 25.2, the point release is based on **Debian 13.7 “Trixie”** and ships the long-term-supported **Linux 6.12 LTS** kernel on the standard ISOs, while a Liquorix-flavored **Linux 7.2** kernel is used on the Xfce AHS (Advanced Hardware Support) ISO.

Highlights include the **Mesa 26.1.4** graphics stack on AHS-enabled builds (backported from Debian Sid), support for Siduction 7.x kernels installable through the MX Package Installer, and the ability for the installer to set `lazytime` in fstab by default on fresh installs. The release also adds polish to the MX Welcome, MX Tools, and custom-toolbox utilities, introduces a new **MX Theme Colors** tool for custom-highlight themes and a **Verify-iso-sig** tool for checking ISO digital signatures. The MX Linux 25 “Infinity” series, which began in November 2025, is notable for its dual SysVinit/systemd init support, Debian's deb822 source format, a Qt 6 port of MX Tools, and Wayland-by-default for the Plasma edition.

---

## 2. Garuda Linux Launches Garuda Nix

On September 20, **Garuda Linux** announced **Garuda Nix**, a standalone project that brings the distribution's familiar desktop configurations, styling, and opinionated defaults to **NixOS**. A key point: Garuda Nix is **not Arch-based** — while the regular Garuda Linux distribution is built on Arch, Garuda Nix uses NixOS as its foundation.

The project evolved from the earlier Garuda Nix Subsystem, originally an add-on that let Garuda users install NixOS on the same partition using separate subvolumes. It has since been rebranded as a standalone distro offering two desktop configurations, **Dr460nized** and **Mokka**, which reuse the same dotfiles as the corresponding Garuda Linux editions. Installation works through the graphical **Calamares** installer or a command-line `install-garuda-nix` utility; either installer can deploy both desktops because the NixOS install is network-based. The setup includes a ready-to-use Nix flake under `/etc/nixos` and incorporates **Chaotic Nyx**, the Nix counterpart to Garuda's well-known Chaotic-AUR repository, for additional prebuilt packages. The CLI installer additionally supports configuring **NixOS Impermanence**, implemented via Btrfs rollbacks on Btrfs systems or a tmpfs root with ext4.

---

## 3. Peppermint OS Begins Shift from X.Org to XLibre

**Peppermint OS**, the lightweight Debian- and Devuan-based distribution built around XFCE, announced on September 21 that it has begun testing an updated Debian edition that replaces the **X.Org Server** with **XLibre** while keeping the X11 display protocol.

Planned for upcoming ISO refreshes, the change has XLibre handle graphical rendering, window drawing, and input devices; the project says testing so far has not uncovered significant compatibility issues. Importantly, the move does **not** signal a transition to Wayland — Peppermint says it has no immediate plans to leave X11, and notes XFCE's development currently targets both X11 and Wayland. The first ISO built this way is the 64-bit Debian flagship nightly image. A notable build-system change accompanies the shift: it's the project's first Debian ISO created **without Debian's traditional live-build tooling**, now starting directly from **mmdebstrap** rather than debootstrap, following the architecture developed for its Devuan edition. The Devuan-based edition is also moving to XLibre and will be released for community testing separately once final fixes land.

---

## 4. GNU Wget 2.3

**GNU Wget 2.3** was released on September 21 as the latest version of the multithreaded successor to the GNU Wget command-line downloader, bringing security hardening, bug fixes, and improved Wget1.x compatibility. New features include converting CSS files with `--convert-links`, support for iframe `srcdoc` plus the `data-src` and `data-srcset` HTML attributes, a new `--progress=dot` option, printing headers without downloading via `--spider/-S`, and support for `Content-Length: 0` in POST, PUT, and PATCH requests per RFC 9110.

On the security front, Wget 2.3 fixes an integer overflow in cookie parsing and a stack overflow during recursive parsing of local files, caps XML parsing recursion at 1024 levels, and only accepts secure cookies from HTTPS. Path-traversal prevention for `Content-Disposition` is improved, with filenames sanitized and reduced to their basename, and Metalink paths are sanitized on Windows. TLS backends received attention too: Wget now validates the purpose of SSL/TLS certificates, GnuTLS accepts system settings (and requires 3.6.5 or newer), OpenSSL gains post-handshake auth, and WolfSSL respects `NO_OLD_TLS`, enables the domain check, and improves OCSP checks. Wget1.x compatibility improved for `--directory-prefix/-P`, `--accept/--reject`, and URL unescaping, and multiple memory leaks were fixed.

---

## 5. Portainer 3.0 Goes Kubernetes-First

**Portainer** confirmed on September 20 that its next major release, **Portainer 3.0**, will shift the platform's development focus to **Kubernetes**, with Docker, Swarm, and Podman becoming secondary. The company says **Portainer 2.45 LTS** will be the final release in the 2.x series, with 3.0 arriving as an STS release followed by a new LTS. New features around the policy engine, GitOps, and observability will mainly target Kubernetes, which has grown to the point that maintaining identical capabilities across Docker, Podman, Swarm, and Kubernetes in one codebase is no longer practical. Users can still connect and manage Docker, Swarm, and Podman in 3.x, but these environments will not receive every new platform feature.

For Docker users, Portainer points to its **Portainer-D2K** compatibility layer, which makes Kubernetes look like a Docker environment and exposes a Docker-compatible API so existing automation and Compose tooling keep working. A migration add-on will convert Docker containers and stacks into Kubernetes manifests for deployment via GitOps. Notably, **Portainer Community Edition (CE)** will stay on the 2.x codebase — there will be no separate CE 3.x — with the free path available through Portainer's existing “3 Nodes Free” Business Edition program. Following community criticism of the announcement, CEO Neil Cresswell clarified the company is not abandoning Docker, though the strategic direction is clearly Kubernetes.

---

## 6. Terminal & Command-Line Tooling

**Kitty 0.49** (September 21) introduced official **custom shader support**, enabling GPU-powered visual effects such as animated backgrounds, focus highlighting, cursor effects, and click animations. Performance is a headline feature: real-world throughput improves by roughly **15–35%**, with text-heavy workloads up to ~35% faster, plain ASCII workloads ~50% faster, and Unicode workloads ~15% faster. UTF-8 decoding was optimized with SIMD (with an AVX-512 decoder offering up to a further 75% for multibyte text on Intel Ice Lake+ and AMD Zen 4+), alpha blending for graphics-protocol images is two to 3.5x faster, and HarfBuzz shaping results are cached. New options include `window_border_radius` for rounded borders, `remap_modifiers`, a proportional-splits sizing policy, a new `kitten @ screenshot` command, and a `kitten @ set-os-window-title` command; several Wayland-specific issues (high-resolution scroll wheel handling, clipboard sharing between isolated containers) were also fixed.

**Rsync 3.5.1** (September 21), arriving about a month after the major 3.5 release, fixes several path-handling regressions: explicit sender paths can again traverse symlinked parent directories, `--files-from` paths are correctly treated as operator-supplied rather than beneath the transfer root, and access to `/dev/stdin`, `/dev/stdout`, `/dev/stderr`, and `/dev/fd/N` inside user namespaces is restored. The release bumps the protocol number to **33**, adding a new 4 KiB logical-block statistic to `--stats`, and adds support for internationalized domain names when compiled with the required library.

---

## 7. Storage & Self-Hosting

**RustFS 1.0** reached general availability on September 19 as the first production-ready release of the open-source, **Apache 2.0**-licensed, S3-compatible distributed object storage platform written in Rust. The milestone arrives at a notable moment: MinIO recently ended maintenance of its open-source products and shifted its commercial offering to a proprietary model, and RustFS positions itself as a permissively-licensed, self-hosted alternative in that gap. The release includes bucket and object lifecycle management, multipart uploads, erasure coding, data tiering, **S3 Tables** with an integrated Apache Iceberg REST Catalog, and access via not just S3 but also WebDAV, the Swift API, FTP/FTPS, and MCP. Security features cover IAM, OIDC, KMS integration, server-side encryption, STS tokens, mTLS, and auditing; it runs on Linux, Windows, and macOS with DEB and RPM packages. Since going open source in July 2025, RustFS reports more than 32,000 GitHub stars, over 10 million Docker Hub pulls, and over 2.7 million deployed instances. A **RustFS 2.0** is planned to expand toward AI-infrastructure storage workloads with S3 Vectors.

**Pangolin 1.23** (September 19) made the open-source, zero-trust remote access platform's **clustering** easier to deploy. DNS resolution and certificate management moved into the main Pangolin container, the deployment process was streamlined, and public docs now cover a two-node clustered setup. High availability is offered through Pangolin's self-service Scale tier and Enterprise plans, with free license keys for personal use and small organizations. Version 1.23 also integrates sites into the main Pangolin CLI (Newt, its lightweight connector, can now run through the same command line), adds a centralized list of all organizations hosted on an instance, and introduces support for multiple server administrator accounts.

---

## 8. Other Releases & Ecosystem

Beyond the headlines above, the week (as tracked in the 9to5Linux Weekly Roundup and Linuxiac Week 38 wrap-up) included **Clonezilla Live 3.3.3-37** with HTTP boot and LUKS2 support, **Raspberry Pi OS 2026-09-15** with a new dock and revamped desktop controls, **Tails 7.13** with faster shutdowns, and **Arch-based Omarchy 4.0.4** making its custom kernel the default. Software releases included Firefox and Thunderbird 156, `GNU Coreutils 9.12` (with faster `sort`, `cut`, and `uniq`), PipeWire 1.6.9, VirtualBox 7.2.18, Calibre 9.15, HPLIP 3.26.6, DXVK 3.1.1, and MariaDB 13.0.2 — with kernel updates across the 7.2, 6.18 LTS, and 6.12 LTS lines. Looking ahead, **Ubuntu 26.10 Beta** is expected in the coming week.

---

## Sources

- 9to5Linux — *MX Linux 25.3 “Infinity” Is Out with Linux Kernel 7.2, Based on Debian 13.7* (September 20, 2026) — https://9to5linux.com/mx-linux-25-3-infinity-is-out-with-linux-kernel-7-2-based-on-debian-13-7
- Linuxiac — *Garuda Linux Launches Garuda Nix for NixOS Users* (September 20, 2026) — https://linuxiac.com/garuda-linux-launches-garuda-nix-for-nixos-users/
- Linuxiac — *Peppermint OS Starts Its Shift from X.Org to XLibre* (September 21, 2026) — https://linuxiac.com/peppermint-os-starts-its-shift-from-x-org-to-xlibre/
- 9to5Linux — *GNU Wget 2.3 Released with New Features, Improvements, and Bug Fixes* (September 21, 2026) — https://9to5linux.com/gnu-wget-2-3-released-with-new-features-improvements-and-bug-fixes
- Linuxiac — *Portainer 3.0 Goes Kubernetes-First, Leaving Docker Secondary* (September 20, 2026) — https://linuxiac.com/portainer-3-0-goes-kubernetes-first-leaving-docker-secondary/
- Linuxiac — *Kitty 0.49 Terminal Emulator Lands With Custom Shaders and Faster Performance* (September 21, 2026) — https://linuxiac.com/kitty-0-49-terminal-emulator-lands-with-custom-shaders-and-faster-performance/
- Linuxiac — *Rsync 3.5.1 Fixes Path Regressions, Adds Protocol 33* (September 21, 2026) — https://linuxiac.com/rsync-3-5-1-fixes-path-regressions-adds-protocol-33/
- Linuxiac — *RustFS 1.0 S3-Compatible Object Storage Reaches GA* (September 19, 2026) — https://linuxiac.com/rustfs-1-0-s3-compatible-object-storage-reaches-ga/
- Linuxiac — *Pangolin 1.23 Tunneled Reverse Proxy Makes High Availability Easier to Deploy* (September 19, 2026) — https://linuxiac.com/pangolin-1-23-tunneled-reverse-proxy-makes-high-availability-easier-to-deploy/
- 9to5Linux — *9to5Linux Weekly Roundup: September 20th, 2026* (September 20, 2026) — https://9to5linux.com/9to5linux-weekly-roundup-september-20th-2026
- Linuxiac — *Linuxiac Weekly Wrap-Up: Week 38, 2026 (September 14 – 20)* (September 20, 2026) — https://linuxiac.com/linuxiac-weekly-wrap-up-week-38-2026-september-14-20/

---

*Report compiled from publicly available web sources on 2026-09-21. Release dates, versions, and figures are as reported by the cited sources and may vary slightly by edition or region.*
