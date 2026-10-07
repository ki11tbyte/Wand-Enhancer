<div align="center">

<img width="170" height="170" alt="image" src="https://github.com/user-attachments/assets/f4001490-eea4-4699-b661-ad4f93fffb6e" />

# WandEnhancer

[![GitLab Mirror](https://img.shields.io/badge/GitLab-mirror-fc6d26?logo=gitlab)]
</div>

<h4>An open-source interoperability tool designed to extend local client-side configurations and improve the UX of the Wand application.</h4>

## 👾 What does it access?

The default .NET patcher modifies files in the selected local Wand installation and contains no update-checking or telemetry network code. Wand itself remains an online application, build tools restore declared dependencies, and the optional Remote Web Panel deliberately starts a LAN HTTP/WebSocket server and uses Wand API/CDN data. An explicit build-time option can include GitHub release notifications; that variant sends a GitHub API request with your IP and a User-Agent when Wand starts, but sends no Wand or account data and never downloads updates. Review the source and build the executable from your own fork; unsigned patching tools can trigger generic antivirus heuristics.

## 💫 What features are improved?

✅ Local environment configuration management <br/>
✅ Automated compatibility adjustments for new client versions <br/>
✅ Advanced layout and theme customization (Client-side only) <br/>
✅ AI Features <br/>
✅ Remote web panel (Remote Connect on mobile) <br/>

## 🌐 Remote Web Panel
WandEnhancer includes a built-in **Remote Web Panel** allowing you to control app features directly from your phone.

### Quick Start:
1. Ensure both your PC and phone are on the **same Wi-Fi network**.
2. Hover over the **Connect** button in the top bar of WandEnhancer.
3. Scan the displayed **QR code** with your phone's camera.

### Troubleshooting & Remote Access:
- **Page isn't loading?** First, ensure both your PC and phone are connected to the **same local network**. Some routers and guest Wi-Fi networks enable client isolation/AP isolation, which blocks devices on the same SSID from reaching each other. If it still does not load, check Windows Firewall and allow inbound traffic on TCP port `3223` for your local network. If Windows marked your connection as **Public**, switching it to **Private** can also help.
- **Using mobile data or a different network?** If you want to use the panel over mobile data (LTE/5G) or from an entirely different network, you can use [Tailscale](https://tailscale.com/) or similar VPN tools.
- The panel uses plain HTTP on port `3223` and has no pairing code. Anyone who can reach that port can view the panel and control the active trainer, so use it only on a trusted LAN/VPN and never expose the port directly to the internet.
- The panel protocol does not include your Wand bearer token or installation-path fields.


### Testing a release candidate

- `master` is the stable source. Select a `feature/rc_*` branch in your fork's **Run workflow** branch selector only when the maintainer explicitly asks for candidate testing. Ensure that branch contains the upstream commit you intend to test; syncing `master` does not update a separate RC branch.
- You do **not** need to open a pull request to this repository to build your fork.
- Record the workflow's source commit SHA, not just `2.0.0.0`: the RC tag, RC branch and a local build may contain different fixes.
- For startup failures, attach `launcher.log` and, if relevant, `launcher.prev.log` from the Wand installation root. They include the build commit and applied patches. Remove personal paths or other private information before sharing.
- Include the exact Wand version and stable/beta channel, selected patches, and whether the failure happened on a fresh install, an update, or Restore. Do not attach executables, account tokens or storage dumps.


---

## ❓ Q&A


- **Where do I download the executable?**
  - From your own fork's **Actions** artifact after running the **Build executable** workflow. Do not download `.exe` files from YouTube descriptions, random mirrors, Discord attachments, or issue comments.
- **Why does Windows Defender or SmartScreen warn about my build?**
  - The GitHub Actions artifact is unsigned and uncommon, so Windows may warn even when the code was built directly from your fork. Review the source, verify the workflow logs, and only run binaries you built yourself.
- **Can I use a binary built by someone else?**
  - You can, but you should treat it as untrusted. This repository cannot verify or support third-party builds.
- **Does this send data anywhere?**
  - The default .NET patcher is fully offline. The optional Remote Web Panel listens on your LAN and may request trainer translations/artwork through Wand's existing API/CDN paths. If you explicitly compile in update notifications, each Wand launch checks GitHub's public releases API and exposes only the normal request metadata, including your IP and User-Agent. There is no telemetry, download, or automatic update.
- **How do I learn about a new version without an in-app update check?**
  - On GitHub choose **Watch → Custom → Releases**, then sync your fork and run **Build executable** when a release is published. You can also opt into compile-time release notifications in the manual workflow.

---
## 🖼️ Screenshots
<img width="1102" height="830" alt="image" src="https://github.com/user-attachments/assets/947539c1-0579-429e-981f-e76c0ef8dca3" />

<div align='center'>


## 📜 License
This project is licensed under the Apache-2.0 - see the [LICENSE](LICENSE.md) file for details.


## ❤️ Support

If you find this project useful, you can support its development using any of the options below 🙌

[![Patreon](https://img.shields.io/badge/Patreon-donate-f96854.svg?logo=patreon)](https://www.patreon.com/kitbyte/gift)
[![USDT TRC20](https://img.shields.io/badge/USDT--TRC20-donate-26a17b.svg?logo=tether)](https://tronscan.org/#/address/TQdvau8pAy5Tg1Aa588tTcPCFgbcHtuoxc)
[![BTC](https://img.shields.io/badge/BTC-donate-f7931a.svg?logo=bitcoin)](https://www.blockchain.com/explorer/addresses/btc/1EZKDcyU8REm9JW5xwXJqSpn5Xaq5yAWWX)
[![ETH](https://img.shields.io/badge/ETH-donate-3c3c3d.svg?logo=ethereum)](https://etherscan.io/address/0xd904d9d0557f88bbb1c4ab3582b4ca0d8a730e8d)


---

> **Legal Disclaimer:**
> This project is a third-party enhancement tool intended solely for educational, research, and local interoperability purposes. It does not distribute any proprietary code or bypass server-side validations. All modifications are performed locally to customize the user's interface.

---
