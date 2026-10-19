<div align="center">

# 1Z-Transfer

**Android ⇄ macOS 局域网文件互传 · 不用数据线、不经过云**
**Wireless file transfer between Android and macOS over your local network — no cable, no cloud.**

[下载 / Download](#下载--download) · [功能 / Features](#功能--features) · [使用 / Usage](#使用--usage) · [常见问题 / FAQ](#常见问题--faq)

</div>

---

## 下载 / Download

到 [**Releases**](https://github.com/F1yPenguin78/1Z-Transfer/releases/latest) 页面下载最新版本 / Grab the latest build from the **Releases** page:

| 平台 / Platform | 文件 / File | 说明 / Notes |
|---|---|---|
| macOS (Apple Silicon) | `1Z-Transfer-v1.5.0.dmg` | 需要 macOS 14+ / requires macOS 14+ |
| Android 8.0+ | `1Z-Transfer-v3.4.apk` | 目标平台 Android 17 / targets Android 17 |

> 两个包都是未签名版本，首次打开需要手动放行，见下方「安装」。
> Both builds are unsigned; see **Install** below for the one-time Gatekeeper / sideload steps.

---

## 功能 / Features

**中文**

- **双向传输**：电脑端可以浏览手机目录、下载、上传；手机端可以选文件推给电脑。
- **局域网直连**：同一 Wi-Fi 下自动发现，最快约 100 MB/s 量级（取决于 Wi-Fi），不经过任何服务器。
- **隔空投送式配对**：手机点「连接」→ 电脑弹窗点「接受」→ 以后免确认。没有账号、没有二维码抄码。
- **断点续传**：传输中断后从断点继续，不重传整个文件。
- **多选与队列**：手机上多选文件一次放入「要发送的文件」，按队列顺序发送。
- **悬浮窗**：在其他 App 里也能随时把文件推给电脑。
- **大图标传输列表**：电脑端以卡片形式罗列传输中的文件，带进度、速度与暂停/继续。
- **可改保存位置**：电脑端主界面右上角随时切换收件目录。
- **热点直连**：酒店、校园网这类会隔离设备的 Wi-Fi 连不通时，让手机开热点、电脑连过去，两端直接互传。

**English**

- **Two-way transfer** — browse the phone from the desktop (download / upload), or push files from the phone to the desktop.
- **Direct over LAN** — auto-discovery on the same Wi-Fi, in the ~100 MB/s range on good Wi-Fi. No server in between.
- **AirDrop-style pairing** — tap *Connect* on the phone, tap *Accept* on the desktop once; remembered afterwards. No accounts, no typing codes.
- **Resumable transfers** — resume from the last byte instead of restarting.
- **Multi-select & queue** — drop several files into the send tray and they go out in order.
- **Floating bubble** — send files while you're in another app.
- **Large-card transfer list** — progress, speed, pause/resume per file.
- **Configurable save folder** — switch the receive directory from the main window at any time.
- **Hotspot fallback** — when a hotel/school Wi-Fi isolates devices, turn on the phone's hotspot instead and the two sides talk directly.

---

## 安装 / Install

**macOS**

1. 打开 dmg，把 `1Z-Transfer.app` 拖进「应用程序」。
2. 首次启动会被 Gatekeeper 拦下（应用未签名）。右键点图标 → **打开** → 再点「打开」；或执行
   `xattr -dr com.apple.quarantine /Applications/1Z-Transfer.app`。
3. 系统若询问「是否允许 1Z-Transfer 访问本地网络」，必须选**允许**，否则手机连不进来。

**macOS (English)** — drag the app into *Applications*. On first launch Gatekeeper blocks it because it is unsigned: right-click → **Open** → **Open**, or run `xattr -dr com.apple.quarantine /Applications/1Z-Transfer.app`. When macOS asks whether 1Z-Transfer may access the local network, choose **Allow** — without it the phone cannot connect.

**Android**

1. 安装 apk（需要允许「安装未知来源应用」）。
2. 首次启动会依次申请「通知」「附近的设备/局域网」权限；**局域网权限必须允许**，否则电脑连不进来。
3. Android 16 及以上还需要允许应用访问本地网络，拒绝后需到系统设置里手动打开。

**Android (English)** — sideload the apk (allow install from unknown sources). On first run it asks for notifications and *Nearby devices / Local network*; the local-network permission is required. On Android 16+ the same permission may also need to be granted in system settings.

---

## 使用 / Usage

**手机 → 电脑 / Phone → Desktop**

1. 两端连同一个 Wi-Fi，电脑打开 1Z-Transfer。
2. 手机点「扫码」扫电脑上的二维码，或点「连接」让电脑弹窗确认。
3. 手机首页下方的大方块里点一下选文件（也可以从别的 App 拖进来），再点右下角**发送**。
4. 文件会落到电脑上你选的保存目录。

**电脑 → 手机 / Desktop → Phone**

1. 手机首页点「服务关」把服务打开（打开后电脑才能连进来）。
2. 电脑左侧点那台手机，就能浏览目录、下载文件、或把电脑上的文件拖进来上传。

**English** — Put both devices on the same Wi-Fi and open the desktop app. On the phone, either scan the QR code shown on the desktop, or tap *Connect* and accept the prompt on the desktop. Pick files into the tray and hit **Send**. For the other direction, turn the phone's service on, then click the device on the left of the desktop window to browse, download, or drop files to upload.

---

## 常见问题 / FAQ

**Q. 文件经过互联网吗？** 不经过。两端在同一个局域网内直连，没有云端、没有账号、没有统计上报。
**Does traffic go through the internet?** No. Both sides talk directly on your local network — no cloud, no account, no telemetry.

**Q. 找不到对方？** 确认在同一个 Wi-Fi。公共网络常开「AP 隔离」，这时改用热点：手机开热点、电脑连过去，两端 App 里都有「手机热点直连」入口。
**Can't find each other?** Make sure you're on the same Wi-Fi. Some routers and most public networks enable *AP isolation*, which blocks LAN peers. In that case turn on the phone's hotspot and connect the computer to it — both apps have a **hotspot** option for exactly this.

**Q. 传输速度多少？** 取决于 Wi-Fi。Wi-Fi 6 局域网实测在几十到一百多 MB/s；远好于 MTP 和蓝牙，后者不适合搬大文件。
**How fast?** Depends on Wi-Fi. On Wi-Fi 6 expect tens to ~100+ MB/s — far faster than MTP, and Bluetooth is not suitable for bulk files.

**Q. 为什么没有签名？** 个人项目，没有付费开发者证书，因此需要手动放行一次。
**Why unsigned?** It's a personal project without a paid developer certificate, so a one-time manual approval is required.

**Q. 支持 Windows 吗？** 目前只提供 macOS 桌面端，Windows 版本尚未发布。
**Windows support?** Only the macOS desktop build is published so far.

---

## 说明 / Notes

- 手机端目标 Android 17（API 37），最低 Android 8.0（API 26）。
- 桌面端为 macOS Apple Silicon 构建。
- 本项目只分发安装包，不在此仓库提供源代码。
- The Android app targets Android 17 (API 37) and supports Android 8.0 (API 26)+. The desktop build is for Apple Silicon macOS. This repository distributes installers only; source code is not published here.
