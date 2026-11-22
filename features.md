# VirtualProg Features

**VirtualProg** is a native virtual machine manager for the Mac. It runs **macOS**, **Linux** and
**Windows** virtual machines on Apple's Virtualization framework, with deep Mac integration, a
full command-line tool and HTTP API, a web dashboard, and companion apps for iPhone, iPad and
Android.

This page lists everything VirtualProg can do. For step-by-step guides, see the
[VirtualProg Help](https://makeprog.com/Products/VirtualProg/help/index.html); for what changed in
each version, see the [changelog](https://makeprog.com/Products/VirtualProg/help/changelog.html).

| | |
|---|---|
| **Mac** | macOS 14.6 Sonoma or later |
| **Apple silicon (M1 or later)** | macOS, Linux and Windows (ARM64) virtual machines |
| **Intel Mac** | Linux virtual machines |
| **Download** | [Mac App Store](https://apps.apple.com/us/app/virtualprog-virtual-machine/id6744131218) · [Free trial](https://makeprog.com/Products/VirtualProg/) |

> Some features need a newer macOS on the Mac. They are marked **macOS 26+** (Tahoe) or
> **macOS 27+** (Golden Gate).

## Contents

1. [Guest operating systems](#guest-operating-systems)
2. [Creating virtual machines](#creating-virtual-machines)
3. [Prism: guest apps as Mac windows](#prism-guest-apps-as-mac-windows)
4. [Guest Tools and Mac integration](#guest-tools-and-mac-integration)
5. [Display, graphics and input](#display-graphics-and-input)
6. [Disks and storage](#disks-and-storage)
7. [Shared folders and file transfer](#shared-folders-and-file-transfer)
8. [USB devices](#usb-devices)
9. [Camera and sound](#camera-and-sound)
10. [Networking](#networking)
11. [Power, startup and lifecycle](#power-startup-and-lifecycle)
12. [High Availability](#high-availability)
13. [Snapshots](#snapshots)
14. [Checkpoints](#checkpoints)
15. [Linked clones](#linked-clones)
16. [Templates and clones](#templates-and-clones)
17. [Import and export](#import-and-export)
18. [Control Center and organization](#control-center-and-organization)
19. [The virtual machine window](#the-virtual-machine-window)
20. [Monitoring, statistics and logs](#monitoring-statistics-and-logs)
21. [Disk Space Analyzer](#disk-space-analyzer)
22. [Image Catalog](#image-catalog)
23. [Serial ports and consoles](#serial-ports-and-consoles)
24. [Linux-specific features](#linux-specific-features)
25. [Security and privacy](#security-and-privacy)
26. [Automation: vpvm command-line tool](#automation-vpvm-command-line-tool)
27. [Automation: HTTP API, webhooks, URL scheme and Shortcuts](#automation-http-api-webhooks-url-scheme-and-shortcuts)
28. [AI: MCP server and Quanta](#ai-mcp-server-and-quanta)
29. [Web Dashboard](#web-dashboard)
30. [iPhone, iPad and Android apps](#iphone-ipad-and-android-apps)
31. [Mac app experience](#mac-app-experience)

---

## Guest operating systems

### macOS virtual machines
- macOS guests from **Monterey** to the latest release (Ventura, Sonoma, Sequoia, Tahoe, Golden Gate),
  on Apple silicon.
- Install from a restore image (`.ipsw`): pick a local file, drag one in, or download it from the
  built-in [Image Catalog](#image-catalog).
- **DFU Restore** installation mode, Apple's hardware-restore path, for when the standard installer
  stalls or fails.
- **Provisioning** *(macOS 27+)*: skip the Setup Assistant; the user account (full name, username,
  password, auto login, remote login/SSH) is created on first boot.
- Mac keyboard and mouse, or legacy USB keyboard and mouse.
- Boot to **Recovery**, or choose the boot disk manually.
- Recovery partition relocation when growing a macOS disk.
- Install macOS without a display window (headless).

### Linux virtual machines
- Any ARM64 Linux on Apple silicon, and Linux on Intel Macs.
- Built-in installer downloads for Ubuntu, Debian, Fedora, Alpine, Kali, CentOS Stream, Rocky Linux,
  NixOS and more, for both architectures.
- Distro presets: Ubuntu, Debian, Fedora, Alpine, Manjaro, openSUSE, Kali, NixOS, Zorin OS.
- Boot from an ISO, or directly from a **kernel, RAM disk and root file system** with custom boot
  arguments.
- See [Linux-specific features](#linux-specific-features) for Rosetta, nested virtualization, memory
  balloon and more.

### Windows virtual machines
- **Windows 11**, **Windows Server 2025** and other Windows ARM64 installers, on Apple silicon.
- **Unattended Install**: Windows 11 or Server 2025 (Standard, Desktop Experience) installs by itself
  with a local account, VirtIO disk and network drivers loaded during Setup, then the Guest Tools.
  The ISO's edition is recognized automatically.
- Virtual **TPM**, so Windows health checks and BitLocker work.
- **VirtualProgTools** disc with all drivers and the VirtualProg agent, installed with one
  `install.cmd`, and automatic updates.
- Windows guests get almost every VirtualProg feature; serial ports are the only exception.

---

## Creating virtual machines

- **Quick Create** wizard: name (with a random-name generator), OS, image, CPUs, memory, disk size and
  headless option; open the full configuration afterwards if needed.
- Image downloads inside Quick Create, with percentage, bytes, speed, time remaining and Cancel.
- **Full configuration** editor for every setting, with validation and inline help.
- **Distro / version picker** that adapts to the chosen OS.
- **Create from a template**, a snapshot, or a checkpoint (as a linked clone).
- **Clone** any stopped VM, with a new MAC address on request.
- **Import** VMs from Parallels Desktop, UTM and VMware Fusion, or open a `.vpvm` bundle from Finder.
- Custom **VM icons** from any image (PNG, JPEG, HEIC…), shown everywhere in the app.
- Notes / description per VM, shown as a tooltip and editable from Quick Info.
- Configuration can be viewed at any time; it's editable while the VM is stopped.

---

## Prism: guest apps as Mac windows

Prism shows a VM's apps as individual Mac windows, with no guest desktop around them. They work with
Mission Control, window switching and full screen like any Mac app.

### Common to all Prism modes
- **Enter Prism** from the VM toolbar, the Virtual Machine menu or the Control Center context menu;
  **Start in Prism** enters it automatically.
- A shared **menu bar icon** and **Dock menu** for every VM in Prism, with a submenu per VM:
  applications (type to search, Return to open), open windows, the app launcher, Power, Devices,
  Configure VM, window actions and Quit All Prism Apps.
- An **app launcher** window listing the guest's applications with their icons.
- **Floating power panels** for power actions, with screen previews; Pause hides Prism windows until
  you resume.
- Prism comes back after Suspend, Restart, a resume, a live checkpoint, or restoring a snapshot taken
  in Prism, unless you chose Exit Prism.
- On exit with apps open: **Keep Running** them for next time, or **Quit Apps**.
- Mac cursors, live window resizing, and copy and paste with Mac apps.

### Prism for Windows
- **Mac Window Frames**: optional Mac title bars with close, minimize and zoom buttons.
- **Hide Windows Taskbar** while in Prism.
- **Left Cmd as Ctrl** so Cmd+C, Cmd+V and Cmd+Z work; Right Cmd stays the Windows key.
- **Multiple monitors**: one Windows monitor per Mac screen (up to 4, or Automatic); drag apps
  between screens.
- macOS **full screen** for Windows apps; Option-click to zoom.
- Start menu, Alt-Tab and Task View, Windows Store apps in the Applications list on every language.
- The Mac menu bar takes the focused Windows app's name; **Quit** (⌘Q) and **Hide** (⌘H) act on it.
- **Drag files** from Finder onto a Prism window (they open in that app), and from Explorer out to
  Finder, with progress and Cancel.
- Windows notifications float on the Mac screen, or appear in Notification Center with
  [Share Notifications](#guest-tools-and-mac-integration).
- Prism fits the Windows resolution to the Mac screen and restores it on exit.

### Prism for Linux
- Wayland and X11 apps (via Xwayland), with their own D-Bus session.
- **Left Cmd as Ctrl**; Right Cmd is the Super key.
- Linux password prompts (such as GParted's or Synaptic's) appear in a Mac window.
- Recently opened apps at the top of the Applications menu.
- Live snapshots and live checkpoints work in Prism.

### Prism for macOS *(macOS 14+ guests)*
- Every regular app's windows appear, including apps opened before entering Prism.
- The guest app's **own menus appear in the Mac menu bar**, with live enabled and checked states.
- Window menu for the traffic lights (Close, Minimize, Zoom, Enter Full Screen) under macOS's
  screen-sharing indicator; Close lets the app ask to save.
- Title-bar double-click follows the Mac's Desktop & Dock setting.
- **Zoom and full screen fill whichever Mac screen** the window is on, including large external
  displays; the guest display is sized for the largest screen while in Prism.
- Sheets, menus, pop-ups and alerts appear with their windows; Command stays Command.

---

## Guest Tools and Mac integration

VirtualProg Guest Tools for **macOS**, **Linux** and **Windows**, installed from a disk VirtualProg
attaches, with **Auto Update Guest Tools** (also at the macOS login window) and one-click **Update**.

| Feature | macOS | Linux | Windows |
|---|:---:|:---:|:---:|
| **Clipboard sharing** (text and pictures) | ✅ | ✅ | ✅ |
| **Copy and paste files and folders**, both ways | ✅ | ✅ | ✅ |
| **Time Sync** (also after pause, suspend and Mac sleep) | ✅ | ✅ | ✅ |
| **Share Mac's Printer** (jobs open the Mac's print dialog) | ✅ | ✅ (CUPS) | ✅ |
| **Share Battery %** (battery level and charging state) | ✅ menu bar | ✅ battery | ✅ battery |
| **Mac camera** in the guest | ✅ | ✅ | ✅ |
| **Live Resources** (guest CPU and memory) | ✅ | ✅ | ✅ |
| **Prism** | ✅ | ✅ | ✅ |
| **Share Notifications** (to Notification Center) | | | ✅ |
| **Graceful shutdown and restart** via the agent | ✅ | ✅ | ✅ |
| **Auto Update Guest Tools** | ✅ | ✅ | ✅ |

- **File copy and paste details:**
  - Mac → VM: on demand, with progress on the file's icon and no size limit (macOS File Provider).
  - VM → Mac: on demand with **Copy and Paste Files from VMs**, with Finder's progress and no size limit.
  - Hidden files such as `.git` are kept; executables stay executable; macOS metadata is skipped.
- **Linux Guest Tools** start at boot on systemd, OpenRC and SysV systems, with no desktop login needed.
- **Windows notifications**: click to open the app, dismiss on either side, follows Focus and the
  Mac's notification settings.
- A **Guest Tools out of date** alert, and Guest Tools version reporting.

---

## Display, graphics and input

- **Auto Resolution**: the guest follows the window size; or **Force Resolution** at a fixed size.
- Resolution presets from the Mac's own display modes, and a resolution menu in the VM toolbar.
- **PPI** setting for macOS guests; **HiDPI (Retina)** for Windows with sharp text.
- **3D Acceleration** for Windows *(experimental, macOS 26+)*: DirectX 11 and OpenGL on the Mac's GPU
  through Metal, with the 3D display driver installed by the Guest Tools.
- **DirectX 12** for Windows through Apple's D3DMetal (Game Porting Toolkit, your own copy) and
  Rosetta.
- Standard Windows display driver with a hardware pointer that moves with the Mac pointer, and low
  CPU screen updates.
- **Hide Mac Pointer** over the VM (Control-Command shows it again).
- **Full screen** with hidden title bar and toolbar, and **Fullscreen on Boot**.
- **Always on Top** pin for the VM window.
- **Window Border** in the VM's tag color.
- **Screenshots** to file or clipboard, with automatic timestamps and an optional screenshot background.
- **Screen recording** of the VM window with ScreenCaptureKit, optional microphone, resolution and
  frame-rate options.
- Keyboard: Mac and Windows shortcut mapping, Super key for Linux, special-keys panel on the web.

---

## Disks and storage

- **Multiple disks** per VM, added new, imported, or attached from existing files (or by drag and drop).
- **Interfaces:** VirtIO or NVMe (macOS and Linux); NVMe, SATA or VirtIO (Windows).
- **Fixed or Dynamic (ASIF) disks** *(macOS 26+)*, and **convert** between them.
- **Resize** disks (including dynamic disks), from the configuration or the Disk Space Analyzer.
- **Read-only** disks; **cache** and **sync** modes (macOS and Linux).
- **Shrink on Trim** and **Compact Disk** for Windows dynamic disks (NTFS, FAT32 and exFAT).
- **CD/DVD drives** (USB or VirtIO), attach and eject while running (read-only).
- **Hot-plug disks** and disk images (read/write) while the VM runs.
- **Network Block Devices** (`nbd://`), with interface, read-only, sync mode and timeout.
- **Show in Finder** for any disk; decimal GB sizes that match Finder.
- Custom storage folder for all VMs.

---

## Shared folders and file transfer

- **Shared folders** (VirtioFS) with custom mount names and read-only option, for macOS, Linux and
  Windows (Z: drive).
- **Add shared folders while running**: session-only folders, attached and detached at any time.
- **Drag and drop** files from Finder onto a VM window to copy them into a shared folder (the VM
  doesn't need to be running).
- Shared folders listed in the VM toolbar and Quick Info, with Show in Finder.
- **Windows → Mac** folder sharing over SMB.
- See also file copy and paste in [Guest Tools](#guest-tools-and-mac-integration) and Prism drag and drop.

---

## USB devices

- **USB passthrough** *(macOS 27+)*: attach and detach Mac USB devices to a running VM.
- **Connect at start**: chosen devices connect every time the VM starts, recognized by vendor,
  product and serial number on any port.
- **Connect as SATA disk** (Windows) so Windows Setup can install onto a USB disk.
- USB webcams, microphones, speakers and headsets in Windows VMs.
- Suspend with USB devices attached; they reconnect on resume.
- USB CD emulation.

---

## Camera and sound

- **Mac camera in the VM** (macOS, Linux, Windows): the Mac's preferred camera (including an iPhone
  with Continuity Camera) or a chosen one; switch it while the VM runs.
- **Sound output and microphone**, each following the Mac's default or a chosen device; switch while
  running.
- **HD Audio** (default) or USB Audio sound card for Windows.
- A disconnected device's choice is kept; the Mac's default is used until it's back.

---

## Networking

- **NAT** and **Bridged** networking, multiple adapters, custom or regenerated **MAC addresses**.
- **Custom networks** *(macOS 26+)*: shared or host-only, subnets, MTU 1280–9000, IPv6 with
  auto-generated ULA prefixes, binding to a physical interface.
- **Static IPs** and **TCP/UDP port forwarding** on custom networks.
- **VLAN (802.1Q)** interfaces as an adapter source (wired Ethernet).
- **Network Manager** window, and automatic updates of VMs when a network changes.
- **Network Topology** diagram *(macOS 26+)*: VMs, adapters, live IP addresses and port forwards,
  with zoom, pan and highlighting.
- **Guest IP address** shown in the app, web, mobile apps and CLI (`vpvm ip`).
- Windows adapters: USB (NCM) or VirtIO (PCI).
- **SSH** settings per VM (username, port, password or private key) for one-click connections.

---

## Power, startup and lifecycle

- **Start, Stop, Shut Down (graceful), Pause, Resume, Restart and Suspend** *(Apple silicon)*.
- **Suspend** saves the VM's memory to disk and resumes exactly where it left off.
- **Auto Start** when VirtualProg launches, with a **startup delay** (0–300 seconds) to stagger VMs.
- **Mac Sleep** action: do nothing, pause, suspend, stop or shut down; resumes on wake.
- **Mac Shutdown** action: do nothing, suspend, stop or shut down.
- **VM Close** action: ask, stop, suspend, shut down, or keep running in the **background**.
- **Auto actions** on inactivity or low battery: pause, suspend, shut down or stop.
- **Auto Pause** with click-to-resume overlay.
- **Schedule**: days of the week with start and stop times, and a global scheduler switch.
- **Headless** VMs, with Open Display to attach a window at any time; pause and restart headless VMs.
- **Server Mode**: VMs start headless, open VM windows go to the background, and informational
  alerts are logged instead of shown.
- Floating **power panels** with previews, Resume and Stop for slow shutdowns.
- **Quit prevention** while VMs run, and running time in the window title.
- Crashed macOS and Linux VMs can be started again at once.

---

## High Availability

- Restart a VM automatically **On Failure** (crash, missed heartbeat, unexpected exit) or **Always**.
- **Heartbeat** through the Guest Tools, a TCP port (SSH, RDP or any service), or both.
- Configurable check interval, misses before restart, grace period after start or wake.
- **Restart limits** within a time window, and an increasing restart delay.
- Status in the app, and `vm.unresponsive`, `vm.ha.restarted` and `vm.ha.failed` webhooks.

---

## Snapshots

- **Full snapshots** of a VM's disks and configuration.
- **Live snapshots** of running, paused or suspended VMs: restoring resumes with apps still open
  (APFS; instant copies).
- **Auto snapshots**: On Start, Daily, Weekly, Monthly or On Shutdown, with a name prefix and
  retention limit.
- **Safety snapshot** before a restore, and **Safe Snapshot Restore** (atomic swap).
- **Discard saved memory** from a live snapshot.
- **Create a VM** or a **template** from any snapshot.
- **Timeline view** (newest to oldest, disk bars, time gaps, manual vs automatic), list and grid views.
- Snapshot **Quick Info** with the full configuration at snapshot time.
- Favorites, tag colors, groups, search, sort and notes.

---

## Checkpoints

*macOS 27+, using Apple's DiskImageKit stacked ASIF images.*

- **Instant, space-efficient save points** that store only changes.
- **Live checkpoints** of running, paused or suspended VMs (macOS, Linux and Windows), and restore
  with apps still open.
- **Restore** and **delete** (with an optional restart), **flatten** one or all checkpoints,
  **discard memory**.
- Overlay sizes, favorites, tag colors, search, list and grid views.
- **Create a linked clone** from any checkpoint.

---

## Linked clones

*macOS 27+.*

- **Fork a VM instantly** without copying its disks; the clone stores only its own changes.
- From the current state, from a checkpoint, or **live** from a running VM.
- Clones of clones to any depth; the parent stays fully usable.
- **Detach** a linked clone into an independent VM (cancellable).
- **Linked Clone Topology** diagram of roots and clones by generation.
- Linked-clone badges in the Control Center.

---

## Templates and clones

- **Templates** from VMs or snapshots; **create VMs** from templates.
- **Editable** templates, **template cloning** and **disk resize** for templates.
- Template **Quick Info**, favorites, tag colors, groups, search, sort and grid view.
- **Clone** VMs with an optional new MAC address; random default names.

---

## Import and export

- **Import from Parallels Desktop, UTM and VMware Fusion** with apps, files and settings; the
  originals are left untouched.
- **Import `.vpvm`** bundles by double-clicking them in Finder.
- **Export** a VM bundle to any folder, with progress.
- **Rename** VMs: bundle, snapshots, logs, configuration and Spotlight index are updated together.

---

## Control Center and organization

- **List and grid views**, with view preferences remembered per view.
- **Favorites**, **Recents** and **tag colors**, with a tag color filter.
- **Groups** for VMs, templates and snapshots, with group start, stop and shut down.
- **Search** and **sort** (name, date created, last used).
- **Batch selection** (Cmd-click) to start, stop, shut down or group several VMs.
- **Extra details** line: CPU, memory, disk usage and next scheduled event.
- **Quick Info** popovers: configuration, disk usage, snapshot and template counts, uptime, 24-hour
  activity bar, shared folders and editable notes.
- **Warnings** for disk usage above 85% and for missing shared folders, images or disks.
- Right-click **device actions** for running VMs: attach and eject images, Guest Tools, shared
  folders, camera and sound.
- Suspend, pause and lock indicators; double-click to start or focus a VM.
- **VM Switcher** (⌃⌥V, customizable): switch between running VMs with thumbnails and the keyboard.

---

## The virtual machine window

- **Compact toolbar** with one Power, Devices and Snapshots button, or the full toolbar.
- Devices: serial ports, USB devices, memory balloon, sound, camera, shared folders, CD/DVD and disks.
- **Quick Info**, **Always on Top**, screenshot and recording buttons, resolution picker.
- Running time in the title bar; status overlays for paused and auto-paused VMs.
- Drag and drop files into shared folders.
- A **Virtual Machine** menu that matches the toolbar, with standard Mac shortcuts.

---

## Monitoring, statistics and logs

- **Live Resources**: guest CPU and memory (and swap where supported) with five-minute charts, for
  macOS, Linux and Windows; host CPU and memory overview. On the Mac, web, iOS, Android, CLI and MCP.
- **Dashboards** per VM and for all VMs: total uptime, sessions, average session length, daily
  activity, recent sessions.
- **Export statistics** as CSV or PNG (matching light or dark theme).
- **Log Viewer** with info/error filters, date range, search, export and live follow (web and CLI).
- **Info Logs** setting, log rotation with a maximum size, and automatic repair of damaged logs.
- **Diagnostic Logs** zip (configuration, statistics, snapshot metadata and logs).
- **macOS widget** (small, medium, large) with live VM status.
- **Notifications** for VM state changes, and a **Dock badge** with the number of running VMs.

---

## Disk Space Analyzer

- Allocated and configured size of every VM, template, snapshot and checkpoint.
- Summary **donut chart**, expandable per-disk breakdown, quick actions.
- **Resize** and **convert** disks, with recovery partition handling for macOS.
- **Export** as CSV or PNG. Also on the web dashboard and in the mobile apps.

---

## Image Catalog

- Built-in catalog of **macOS restore images** and **Linux ISOs**, with download status and progress.
- **Custom entries** with your own download URLs.
- **Untracked files** view to find and delete images no VM, snapshot or template uses.
- Show in Finder, delete, cancel downloads; from the Mac, web, mobile apps and CLI.

---

## Serial ports and consoles

*macOS and Linux VMs.*

- Serial ports in **Console** mode (built-in terminal) or **File** mode (log file).
- **Terminal**: full VT100/xterm emulation, ANSI colors, scrollback, GPU-accelerated rendering,
  themes, Ctrl+C and function keys, password masking.
- Open serial ports from the Control Center for headless VMs.
- **Web Console** in the browser with replay of recent output, search, and multiple viewers; log
  download for File-mode ports.

---

## Linux-specific features

- **Rosetta** to run x86-64 Linux binaries on Apple silicon, with caching and a custom share name.
- **Nested virtualization** (M3 or later).
- **Memory balloon**: change guest memory while running, from the Mac, web, mobile apps and CLI.
- **VirtIO entropy** device control.
- **Kernel and RAM disk boot** with boot arguments and root file system.

---

## Security and privacy

- **Password-protected VMs** with **Touch ID** unlock and automatic re-lock.
- Per-VM permissions for **screenshots**, **screen recording** and **usage statistics**.
- **Permissions** screen for microphone, camera, screen recording and local network.
- Built-in server security:
  - **Token authentication** (master token, regenerate and copy).
  - **Scoped access tokens**: Operator or Admin, per VM, extended permissions, expiry, rotate,
    disable and revoke.
  - **HTTPS/TLS** with an imported PKCS#12 certificate or a generated **self-signed certificate**.
  - **Two-factor authentication** (TOTP) with recovery codes.
  - **IP allowlist** with IPv4/IPv6 addresses and CIDR ranges; **External Access** switch.
  - **Active Web Clients** window.
- Screen recording is limited to VirtualProg's own windows.

---

## Automation: vpvm command-line tool

`vpvm` for **macOS**, plus remote clients for **Windows** and **Linux**.

- **Every action and setting**: power, create, clone, rename, delete, configuration of every section,
  disks, networks, CD/DVD, serial ports, NBD, USB, webhooks, SSH, camera and sound.
- Snapshots, checkpoints (`--live`, `flatten`, `discardmemory`), linked clones (`detach`),
  templates, images and the catalog, networks, tokens, Mac server settings.
- `list`, `watch` (live monitor), `info`, `ip`, `stats`, `status`, `resources`, `screenshot`,
  `logs --follow`, `balloon`, `usb`, `camera`, `sound`, `guest-tools`.
- **Bulk operations** with comma-separated VM names.
- **JSON output** (`--format json`) for scripts and `jq`.
- **Remote control** of another Mac (`--server`, `--port`, `--token`, `--secure`, `VPVM_*`
  variables) and **named profiles** in `~/.vpvmrc`.
- **Interactive shell** with history and line editing; contextual help with values and examples.
- Lock and unlock password-protected VMs.

---

## Automation: HTTP API, webhooks, URL scheme and Shortcuts

- **HTTP API** for everything the app does, with WebSocket screen (JPEG, H.264, HEVC), input and
  serial console streams.
- **Webhooks**: POST JSON to any URLs on `vm.started`, `vm.stopped`, `vm.paused`, `vm.suspended`,
  `vm.crashed` and High Availability events.
- **URL scheme** `virtualprog://control/<action>?name=<VM>` for Raycast, Alfred, Shortcuts and scripts.
- **App Shortcuts, Siri and Spotlight**: Launch Virtual Machine, New Virtual Machine, Take Snapshot,
  Create Template, Open Dashboard, Open Snapshots, Open Templates, Open Settings.
- **Spotlight indexing** of VM names.

---

## AI: MCP server and Quanta

- **MCP server** for Claude, Cursor, GitHub Copilot and other assistants, on macOS, Windows and
  Linux (remote).
  - Access modes: read, operate (default) and full, plus destructive, admin and secrets options.
  - Limit the assistant to named VMs; activity log.
  - The assistant can take screenshots to see a VM's screen.
- **Quanta AI chat** *(macOS 27+)*: manage VMs in your own words with Apple Intelligence, on device or
  with Private Cloud Compute. Power, details, creation, settings, snapshots, checkpoints, templates,
  images and opening windows; asks before deleting or restoring. Also in the web dashboard and the
  iPhone, iPad and Android apps, sharing the same chats.

---

## Web Dashboard

Manage VirtualProg from any browser, on your network or remotely.

- **Virtual machines**: list and grid, groups, favorites, tag colors, create and configure VMs, power
  actions with progress, IP addresses, password-protected VMs.
- **Remote screen**: live display with **H.265, H.264, PNG or JPEG**, switching codecs on the fly,
  Auto FPS, Fit to Window, HiDPI, HTTP fallback, keyboard and mouse, special keys, touch controls,
  screenshots, resolution changes, connection stats.
- **Web SSH** terminal and SSH quick connect; **Web Console** for serial ports.
- Snapshots (with timeline), checkpoints, linked clones, templates, Image Catalog, networks and
  topology, Disk Space, logs (live), Live Resources, statistics, access tokens.
- **Web CLI** terminal with tab completion, and **Quanta**.
- Mac server settings, accent color, light and dark themes, keyboard shortcuts panel.
- Login with token and optional 2FA; scoped tokens hide what they can't use.

---

## iPhone, iPad and Android apps

*VirtualProg Remote Control: iOS 17+ and Android 8.0+.*

- Connect to one or more Macs, on the network or over the internet, with HTTPS.
- VMs in list or grid with search, filters, sort, bulk actions, creation and details.
- **Live screen** with keyboard, stream settings, USB and memory balloon.
- Serial console, SSH terminal and the in-app command line.
- Snapshots (list and timeline), checkpoints, linked clones and topology, templates, networks,
  Image Catalog, Disk Space, logs, statistics and Live Resources.
- Access tokens, two-factor authentication and **Face ID** / biometric lock.
- **Shortcuts and Siri** (iOS) and launcher shortcuts (Android).
- Sidebar layouts for iPad, iPhone Duo, Android tablets and unfolded foldables.

---

## Mac app experience

- Native SwiftUI app, at home on macOS Tahoe's Liquid Glass design, with light, dark or system
  appearance.
- **Menu bar icon** and **Dock menu** with quick VM actions; **Tools** menu for every utility.
- **Launch at Login**, minimize instead of quit on Control Center close.
- **Onboarding** for first-time setup, including permissions and HTTPS.
- **Built-in offline Help** with context-aware pages, and **What's New** / Version History.
- **Software update check** at launch.
- **Open or Show in Finder** after every export.
- Download the command-line tool from the Help menu.

---

<sub>Apple, Mac, macOS, iPhone, iPad, Siri, Spotlight and Touch ID are trademarks of Apple Inc.
Windows and DirectX are trademarks of Microsoft Corporation. Android is a trademark of Google LLC.</sub>
