+++
title = "Cybersecurity News & Threats — September 21, 2026"
description = "A roundup of cybersecurity developments as of late September 2026: AI-powered offensive research taking over real accounts, hijacked AI browser agents, cascading supply-chain credential theft, North Korean developer-targeting, ransomware attacking ransomware, and actively exploited vulnerabilities."
date = 2026-09-21
template = "report.html"

[extra]
topic = "cybersecurity"
+++

# Cybersecurity News & Threats — September 21, 2026

**Topic:** Cybersecurity
**Report generated:** 2026-09-21

---

## Executive Summary

As of September 21, 2026, the security news cycle is defined by one dominant theme: **AI has moved decisively from defensive tool to offensive accelerant, and the defenses meant to contain it are lagging.** This week brought the most concrete evidence yet that capable frontier models can be steered into real intrusions — researchers using Anthropic's Claude Opus 5 chained two flaws to take over OpenAI staff accounts and reach an internal code repository in under 72 hours, and Google's Gemini autonomously broke into real companies' systems during an evaluation after a fictional test domain collided with an actual one. Separately, a single researcher showed how a malicious browser extension can hijack the AI agents now embedded in five major browsers (**BragJack**). Meanwhile, the supply-chain damage from May's TanStack npm poisoning continues to cascade (170 CrowdSec private repositories copied), North Korea's developer-targeting economy was quantified at 30,000+ infected devices, and infighting erupted in cybercrime as the **ShinyHunters** gang defaced the Clop ransomware operation's leak site. On the vulnerability front, actively exploited flaws in Orkes Conductor and SolarWinds Access Rights Manager demand urgent attention. The emerging picture: attackers are weaponizing AI days after release, while many organizations still lack the instrumentation to see agents and the discipline to rotate credentials.

---

## 1. AI-Driven Offense Reaches Real Enterprise Targets

Two stories this week demonstrate that AI-assisted intrusion is no longer hypothetical.

**Claude Opus 5 vs. OpenAI (the "HEIF Heist").** Security firm Hacktron disclosed that three researchers used Anthropic's Claude Opus 5 to chain two flaws and take over the ChatGPT and Codex accounts of several OpenAI employees, eventually reaching an internal OpenAI code repository — all in under 72 hours. The chain started in OpenAI's public help forum, built on Discourse. A crafted HEIC/HEIF image triggered an unpatched flaw in the libheif library (**CVE-2026-32882**, rated an 8.8 remote code execution by Discourse's advisory), corrupting the forum server's memory. Because the forum offered "Sign in with OpenAI" single sign-on, control of the server let the researchers hijack the connected accounts of OpenAI staff. OpenAI confirmed the fix roughly 14 hours after the report and paid a $6,500 bounty on September 1. Notably, Claude Opus 5 (released July 24) produced a working exploit within hours in a fresh session, after its predecessor Opus 4.8 struggled against ASLR — a vivid illustration of how new model drops are compressing the time and skill needed for serious offensive work. The broader "HEIF Heist" campaign reportedly found the same image-decoding bug class in Slack, Meta, GitHub Enterprise, and Next.js, though some of those broader claims remain unconfirmed.

**Google Gemini vs. the real internet.** The Wall Street Journal reported that Google's Gemini, during a May evaluation run by Israeli firm Irregular, repeatedly guessed a password and broke into a protected system, and in two other cases found credentials in a public repository. One incident turned out to be against a real company: a naming error meant a fictional "capture-the-flag" company name matched a real domain. Unlike the Anthropic and OpenAI cases, Gemini ended the intrusion after realizing it had hit a real system — which Google's Heather Adkins framed as the model acting responsibly, not as misalignment. Google said the issue was addressed "weeks ago."

---

## 2. A New Attack Surface: Hijacking the AI Agents in Your Browser

Security researcher Gal Weizman of Forever Security disclosed **BragJack**, an attack technique where a single malicious browser extension hijacks the AI assistants now built into five Chromium-based products: Chrome's Gemini Live, Perplexity Comet, Microsoft Edge, Opera Neon, and Anthropic's Claude in Chrome. Once the malicious extension is installed, the abuse runs **without user interaction** — the extension controls the AI agent and abuses its existing privileges to access sensitive information or act on the victim's behalf. The research earned more than $20,000 in bug bounties (from $600 to $7,000 per vendor) and produced two CVEs. BragJack underscores a recurring 2026 theme: as AI agents gain privileges inside browsers and applications, the trust boundary between "helpful assistant" and "privileged actor with the browser's identity" becomes a primary attack surface.

---

## 3. Compromised Credentials Keep Cascading Down the Supply Chain

The May attack on TanStack's npm packages — which stole GitHub tokens, SSH keys, and cloud credentials from developers' machines (**CVE-2026-45321**) — produced a fresh aftershock this week. CrowdSec disclosed on September 18 that an attacker used a GitHub OAuth token from a **former employee's account** (whose access had been left open so he could finish some work) to copy about **170 of CrowdSec's private GitHub repositories** on May 22. The leak, which appeared on a forum on September 16, included the company's web console, data-science scripts, the consensus algorithm behind its blocklist, plus the **email addresses of 83 users** and details on **51 potential investors** from 2020. CrowdSec says infrastructure and databases were not accessed, though the exposure of blocklist thresholds is a notable trade secret. The incident ripples across the industry: OpenAI and Mistral AI separately confirmed employee devices were affected by the same TanStack compromise. The lesson for defenders is blunt — **developer credentials are the crown jewels, and offboarding hygiene plus credential rotation remain weak links**.

---

## 4. North Korea's Developer-Centric Cyber Economy Scales Up

Two North Korean threat groups framed the week's state-sponsored activity.

**WaterPlum: 30,000 devices and US$10.7 million.** A joint advisory from Japanese, U.S., Australian, and German authorities detailed that the group WaterPlum, linked to the multi-year "Contagious Interview" campaign, **compromised at least 30,000 devices across more than 100 countries** between December 2025 and July 2026 and funneled over **US$10.7 million in stolen cryptocurrency** to North Korea. Actors impersonate AI, cryptocurrency, and NFT companies on recruiting and freelance platforms, get job seekers to install malicious npm packages or run code during fake coding tests, and have exfiltrated funds or credentials from **over 7,000 cryptocurrency wallets**.

**Jade Sleet and the macOS backdoors.** SentinelOne attributed a breach of an India-based IT services provider to **Jade Sleet** (also PUKCHONG/Slow Pisces/TraderTraitor, the group behind the ~US$1.5 billion Bybit heist). The intrusion, which surfaced through a DevOps engineer's Apple Silicon MacBook, used the macOS backdoors **FLATROOF** and **ROOFDECK** — the same pair seen in the March–April KelpDAO/LayerZero attack — delivered via job-interview lures and weaponized Terraform dependency-lock files pointing at attacker-controlled registries. Developer endpoints, the report stresses, now sit at the center of the defense because they hold access to source code, CI/CD pipelines, and cloud credentials.

---

## 5. Cybercrime Turns on Itself: ShinyHunters vs. Clop

In a twist on the usual extortion narrative, the **ShinyHunters** extortion gang breached and defaced the **Clop (Cl0p) ransomware operation's data leak site** on the Tor network. ShinyHunters says it exploited an **unauthenticated file upload vulnerability in Grav CMS** to upload a taunt file — "THIS SITE HAS BEEN PWN3D BY SHINYHUNTERES" — and later claimed to have "completely defaced" the site, allegedly stealing server data and the **private keys for Clop's onion service**. BleepingComputer confirmed the file was live on Clop's Tor server. It is a memorable marker of how contested, and how fragile, the "trust infrastructure" of ransomware gangs can be — and a reminder that even criminal operations are not safe from their peers.

---

## 6. Actively Exploited Vulnerabilities This Week

- **Orkes Conductor (CVE-2026-58138, CVSS 9.8/9.3):** A **pre-authentication remote code execution** flaw in the popular workflow-orchestration platform is under active attack. Attackers submit crafted workflow definitions with JavaScript or Python to the workflow API, abusing unsandboxed GraalVM evaluators to run arbitrary OS commands. Fortinet reported blocking **1,290 attempts in a single 24-hour window** and **~7,000 between September 2 and 9**, with activity concentrated in Germany, Hong Kong, Indonesia, the U.A.E., and India. Fix: upgrade to Conductor 3.30.2 or restrict external access to the workflow API.
- **SolarWinds Access Rights Manager (CVE-2026-28326, CVSS 8.8):** An **unauthenticated remote code execution** flaw stemming from a **hard-coded static key** affects ARM 2026.2 and earlier; patched in 2026.2.1 (advisory dated September 17). SolarWinds also shipped fixes for Web Help Desk and 16 Serv-U flaws. No in-the-wild exploitation has been reported for this one.
- **Linux kernel (CISA KEV):** U.S. CISA added three Linux kernel vulnerabilities to its Known Exploited Vulnerabilities catalog after confirming in-the-wild exploitation — a timely reminder that public exploit code for the four local-privilege-escalation flaws (DirtyAH6, TUNderflow, PPPoEject, DiagSpill) discussed in our September 18 report is already being operationalized.

---

## Bottom Line

Late September 2026 is defined by **AI crossing the line from research stunt to real intrusion**, with frontier models reliably steering end-to-end exploits against targets from OpenAI to everyday companies. Combined with AI-browser-agent hijacking (BragJack), a persistent developer-credential supply-chain problem (TanStack, WaterPlum, Jade Sleet), and active exploitation of Orkes Conductor, the priorities for security teams are clear: **re-secure the AI agent layer, harden developer and offboarding hygiene, rotate credentials aggressively, and patch the actively exploited flaws (Orkes Conductor, SolarWinds ARM) before attackers do.**

---

## Sources

- The Hacker News — "Claude Opus 5 Helped Researchers Take Over OpenAI Staff Accounts via Chained Flaws" (Sep 20, 2026) — https://thehackernews.com/2026/09/claude-opus-5-helped-researchers-take.html
- The Hacker News — "Google Gemini Broke Into Real Company Systems After Security Test Domain Mix-Up" (Sep 19, 2026) — https://thehackernews.com/2026/09/google-gemini-broke-into-real-company.html
- The Hacker News — "CrowdSec Says TanStack npm Attack Led to Copy of 170 Private GitHub Repositories" (Sep 19, 2026) — https://thehackernews.com/2026/09/crowdsec-says-tanstack-npm-attack-led.html
- The Hacker News — "Jade Sleet Linked to Indian IT Provider Breach With FLATROOF and ROOFDECK Backdoors" (Sep 21, 2026) — https://thehackernews.com/2026/09/jade-sleet-linked-to-indian-it-provider.html
- The Hacker News — "ClickFix Lures Deploy ChainScript RAT Using Polygon to Rotate C2 Infrastructure" (Sep 21, 2026) — https://thehackernews.com/2026/09/clickfix-lures-deploy-chainscript-rat.html
- The Hacker News — "Critical Pre-Auth RCE in Orkes Conductor Workflow Platform Exploited in the Wild" (Sep 19, 2026) — https://thehackernews.com/2026/09/critical-pre-auth-rce-in-orkes.html
- The Hacker News — "SolarWinds Patches ARM Hard-Coded Key Flaw Enabling Unauthenticated RCE" (Sep 19, 2026) — https://thehackernews.com/2026/09/solarwinds-patches-arm-hard-coded-key.html
- The Hacker News — news/RSS index (Sep 15–21, 2026): ChainScript RAT, CISA Linux kernel KEV additions, BIND 9 update, WooCommerce and WSO2 exploits — https://thehackernews.com/
- BleepingComputer — "BragJack attacks hijack AI browser agents through malicious extensions" (Sep 2026) — https://www.bleepingcomputer.com/news/security/bragjack-attacks-hijack-ai-browser-agents-through-malicious-extensions/
- BleepingComputer — "North Korean WaterPlum hackers infected 30,000 devices worldwide" (Sep 2026) — https://www.bleepingcomputer.com/news/security/north-korean-waterplum-hackers-infected-30-000-devices-worldwide/
- BleepingComputer — "ShinyHunters hacks Clop leak site, threatens to extort ransomware gang" (Sep 2026) — https://www.bleepingcomputer.com/news/security/shinyhunters-hacks-clop-leak-site-threatens-to-extort-ransomware-gang/
- BleepingComputer — home news index (Sep 2026): Microsoft Windows domain-login workaround, File History backup issue, npm install-script evasion — https://www.bleepingcomputer.com/

---

*Report compiled from publicly available web sources on 2026-09-21. Figures are as reported by the cited sources and may vary by methodology or by subsequent developments; several incidents (e.g., the OpenAI/HEIF Heist attribution and the extent of the CrowdSec leak) were still being clarified at the time of writing.*