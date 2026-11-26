<div align="center">

<img src="https://makeprog.com/images/Products/VirtualProg/images/VirtualProg.png" alt="VirtualProg" width="128" height="128">

# VirtualProg

**Issues & Feature Requests**

Run macOS, Linux and Windows virtual machines on your Mac, natively.

[![Download on the Mac App Store](https://img.shields.io/badge/Mac_App_Store-Download-0D96F6?style=for-the-badge&logo=apple&logoColor=white)](https://apps.apple.com/us/app/virtualprog-virtual-machine/id6744131218)
[![Free Trial](https://img.shields.io/badge/Free_Trial-DMG-34C759?style=for-the-badge&logo=apple&logoColor=white)](https://makeprog.com/Products/VirtualProg/VirtualProg.dmg)
[![Help](https://img.shields.io/badge/Help-Docs-8E44AD?style=for-the-badge&logo=readthedocs&logoColor=white)](https://makeprog.com/Products/VirtualProg/help/index.html)

[![macOS 14.6+](https://img.shields.io/badge/macOS-14.6%2B-black?logo=apple)](https://makeprog.com/Products/VirtualProg/help/getting-started.html)
[![Apple silicon & Intel](https://img.shields.io/badge/Apple_silicon_%26_Intel-supported-555555)](https://makeprog.com/Products/VirtualProg/help/faq.html)
[![Open issues](https://img.shields.io/github/issues/last-Programmer/VirtualProg?label=open%20issues)](https://github.com/last-Programmer/VirtualProg/issues)
[![Feature requests](https://img.shields.io/github/issues/last-Programmer/VirtualProg/enhancement?label=feature%20requests&color=a2eeef)](https://github.com/last-Programmer/VirtualProg/issues?q=is%3Aopen+label%3Aenhancement)

[**Report a Bug**](https://github.com/last-Programmer/VirtualProg/issues/new?template=bug_report.yml) ·
[**Request a Feature**](https://github.com/last-Programmer/VirtualProg/issues/new?template=feature_request.yml) ·
[**Ask a Question**](https://github.com/last-Programmer/VirtualProg/issues/new?template=question.yml) ·
[**All Features**](https://makeprog.com/Products/VirtualProg/help/features.html) ·
[**Enterprise Use**](https://makeprog.com/Products/VirtualProg/help/enterprise.html) ·
[**Changelog**](https://makeprog.com/Products/VirtualProg/help/changelog.html)

</div>

---

This is the official public tracker for **[VirtualProg](https://makeprog.com/Products/VirtualProg/)**,
made by **[MakeProg](https://makeprog.com)**. Report bugs, suggest features and ask questions here;
every issue is read by the people who build VirtualProg.

> [!NOTE]
> VirtualProg's source code isn't public. This repository holds **issues and feature requests only**.

## Contents

- [About VirtualProg](#about-virtualprog)
- [Get VirtualProg](#get-virtualprog)
- [Before you open an issue](#before-you-open-an-issue)
- [Reporting a bug](#reporting-a-bug)
- [Requesting a feature](#requesting-a-feature)
- [Please don't post here](#please-dont-post-here)
- [How issues are handled](#how-issues-are-handled)
- [Labels](#labels)
- [Be kind](#be-kind)

## About VirtualProg

VirtualProg is a native virtual machine manager for macOS, built on Apple's Virtualization
framework. It's designed to feel like a Mac app, and to scale from one VM on a MacBook to a
fleet of them controlled from a browser or a phone.

| | |
|---|---|
| 🖥️ **Every major OS** | macOS, Linux and Windows 11 / Windows Server 2025 (ARM64) on Apple silicon; Linux on Intel Macs. |
| 🪟 **Prism** | Windows, Linux and macOS apps open as their own Mac windows, with the Dock, menu bar and Mission Control. |
| ⚡ **Live Snapshots** | Snapshot a running, paused or suspended VM without shutting it down; restoring it resumes with your apps still open. Plus scheduled auto snapshots and a snapshot timeline. |
| 📍 **Live Checkpoints** | Instant, space-efficient save points that store only what changed, taken while the VM runs, and restored in seconds (macOS 27+). |
| 🔗 **Linked Clones & Live Linked Clones** | Fork a VM in seconds without copying its disks, from its current state, a checkpoint, or live from a running VM; clones of clones to any depth, and detach a clone into its own VM (macOS 27+). |
| 🛡️ **High Availability** | Restart a VM automatically after a crash, an unexpected quit or a missed heartbeat (through the Guest Tools or a network port), with restart limits and webhooks. |
| ✨ **Quanta AI** | Manage your VMs by asking in your own words, with Apple Intelligence on your Mac or Private Cloud Compute; on the Mac, the web, iPhone, iPad and Android (macOS 27+). |
| 🧩 **Templates & clones** | Reusable templates, quick clones, Quick Create and an image catalog to get started fast. |
| 🔌 **Integration** | Shared clipboard and folders, audio, the Mac's camera, USB passthrough (macOS 27+), Rosetta for Linux. |
| 🌐 **Networking** | NAT and bridged networks, custom Shared and Host-Only networks with static IPs, port forwarding, IPv6 and custom MTU, VLAN (802.1Q), a network manager and live topology view, serial consoles and Web SSH. |
| ⌨️ **Automation** | The `vpvm` command-line tool (macOS, Windows, Linux), an HTTP API with scoped access tokens, an MCP server for Claude, Cursor and GitHub Copilot, webhooks, URL schemes and Shortcuts. |
| 🌍 **Anywhere** | A full web dashboard in any browser, and companion apps for iPhone, iPad and Android. |
| 📊 **Insight** | Live CPU and memory charts, usage statistics, a log viewer and a disk space analyzer. |

See the [full feature list](https://makeprog.com/Products/VirtualProg/help/features.html) and the
[Help](https://makeprog.com/Products/VirtualProg/help/index.html) for details. Deploying VirtualProg
across a team or organization? See [Enterprise Use](https://makeprog.com/Products/VirtualProg/help/enterprise.html).

## Get VirtualProg

| | Where | Notes |
|---|---|---|
| **Mac** | [Mac App Store](https://apps.apple.com/us/app/virtualprog-virtual-machine/id6744131218) | Updates through the App Store. |
| **Mac (trial)** | [VirtualProg.dmg](https://makeprog.com/Products/VirtualProg/VirtualProg.dmg) | Free trial, notarized by Apple. |
| **iPhone & iPad** | [App Store](https://apps.apple.com/us/app/virtualprog-remote-control/id6816698503) | Remote control for your Mac's VMs. |
| **Android** | [Google Play](https://play.google.com/store/apps/details?id=com.makeprog.virtualprog) | Remote control for your Mac's VMs. |

**Requirements:** macOS 14.6 Sonoma or later. macOS and Windows VMs need an Apple silicon Mac
(M1 or later); some features need a newer macOS, as the Help notes.

## Before you open an issue

1. **Update VirtualProg.** Your issue may already be fixed; the
   [changelog](https://makeprog.com/Products/VirtualProg/help/changelog.html) lists what changed.
2. **Search the [existing issues](https://github.com/last-Programmer/VirtualProg/issues?q=is%3Aissue)**,
   open and closed. If one matches, add a 👍 or a comment with your details instead of opening a
   duplicate: it helps us see how many people it affects.
3. **Check the [Troubleshooting](https://makeprog.com/Products/VirtualProg/help/troubleshooting.html)
   guide and the [FAQ](https://makeprog.com/Products/VirtualProg/help/faq.html).** Many common
   problems (permissions, networking, Guest Tools) have a quick fix there.

## Reporting a bug

[**Open a bug report →**](https://github.com/last-Programmer/VirtualProg/issues/new?template=bug_report.yml)

The form asks for everything below. A complete report is usually a faster fix.

| What | Where to find it |
|---|---|
| **VirtualProg version and build** | **VirtualProg → About VirtualProg**, e.g. 2.21 (2.89); and App Store or trial |
| **macOS version and Mac model** | **Apple menu → About This Mac**, e.g. macOS 26.2, MacBook Air M4 |
| **The guest** | OS and version (e.g. Ubuntu 24.04, macOS 26, Windows 11) and how it was made: Quick Create, ISO, restore image, template, or an import from Parallels, UTM or VMware |
| **Guest Tools version** | If the VM has them, and the issue involves clipboard, folders, Prism or display |
| **What happened** | What you did, what you expected, what happened instead, and the exact error message |
| **Steps to reproduce** | The shortest sequence that shows the problem, and whether it happens every time |
| **Logs** | **Help → Logs**, select the VM, then **Export**. Check them before attaching (see below) |

> [!TIP]
> A screenshot or a short screen recording often says more than a paragraph. VirtualProg can record
> a VM's screen itself ([Record Video](https://makeprog.com/Products/VirtualProg/help/recordvideo.html)).

If you'd rather not attach logs publicly, email them to **support@makeprog.com** and mention the
issue number.

## Requesting a feature

[**Request a feature →**](https://github.com/last-Programmer/VirtualProg/issues/new?template=feature_request.yml)

Feature requests are welcome, and they shape what comes next. The most useful ones describe
**the problem you're solving**, not only the button you'd like:

> ✅ "I test my app on three Linux distributions every night and want each run to start from the
> same clean state, then keep the last three results."
>
> ❌ "Add a schedule button."

The first tells us what to build and lets us find the best way to do it. Upvote existing
requests with 👍: the [most requested features](https://github.com/last-Programmer/VirtualProg/issues?q=is%3Aopen+label%3Aenhancement+sort%3Areactions-%2B1-desc)
are the first we look at.

## Please don't post here

> [!WARNING]
> This repository is public. Anything you post can be read by anyone.

- **Purchases, refunds or your App Store account.** Email **support@makeprog.com**.
- **Passwords, SSH keys, access tokens, TOTP secrets or license details.** Check screenshots and
  logs before attaching them: logs can contain file paths, VM names and network addresses.
- **Security vulnerabilities.** Please report them privately; see the [security policy](SECURITY.md).

## How issues are handled

1. **Triage.** New issues are read and labelled, usually within a few days. If something is
   missing we'll ask, and label the issue `needs info`.
2. **Priority.** Bugs that lose data, stop VMs from starting, or affect many people come first.
   Feature requests are weighed by how many people need them (👍) and how well they fit VirtualProg.
3. **Fix.** Fixes and new features ship in VirtualProg updates. The issue is closed with a note
   of the version that includes them, and the
   [changelog](https://makeprog.com/Products/VirtualProg/help/changelog.html) says what changed.

VirtualProg is made by a small independent team, so we can't promise a reply time, but every
issue is read.

## Labels

| Label | Meaning |
|---|---|
| `bug` | Something isn't working as it should |
| `enhancement` | A new feature or an improvement |
| `question` | A question about using VirtualProg |
| `needs info` | Waiting for more details from the reporter |
| `macOS guest` · `Linux guest` · `Windows guest` | Specific to one guest OS |
| `Prism` | Guest apps as Mac windows |
| `documentation` | The Help or the website |
| `duplicate` · `invalid` · `wontfix` | Closed without a change, with a note saying why |

## Be kind

Be respectful and constructive; everyone here is trying to make VirtualProg better. Issues are for
VirtualProg itself. General questions about macOS, Apple's Virtualization framework or a guest OS
are better asked in those communities.

---

<div align="center">

**[VirtualProg](https://makeprog.com/Products/VirtualProg/)** · Made by **[MakeProg](https://makeprog.com)** ·
[Help](https://makeprog.com/Products/VirtualProg/help/index.html) ·
[support@makeprog.com](mailto:support@makeprog.com)

<sub>Apple, Mac, macOS, iPhone and iPad are trademarks of Apple Inc. Windows is a trademark of Microsoft
Corporation. Android and Google Play are trademarks of Google LLC.</sub>

</div>
