<div align="center">

# FramePure — Client-Side Video Packaging Studio

**Lossless HEVC & 4K 120FPS Video Packaging for TikTok**

[![Live Studio](https://img.shields.io/badge/Live_Studio-framepure.pages.dev-10B981?style=for-the-badge&logo=cloudflare&logoColor=white)](https://framepure.pages.dev)
[![Telegram](https://img.shields.io/badge/Telegram-@harithwyd-26A5E4?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/harithwyd)
[![GitHub](https://img.shields.io/badge/GitHub-XC0D3--X-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/XC0D3-X)

🌐 **Live Website:** **[https://framepure.pages.dev](https://framepure.pages.dev)**

</div>

---

## Overview
**FramePure** is a client-side MP4/MOV video packaging utility built to prepare **720p, 1080p, and 4K 120FPS (SDR & HDR10/HLG)** master files for TikTok without triggering destructive platform re-compression.

## Core Capabilities
- **100% On-Device Processing:** Every byte is inspected and remuxed directly in local browser memory. Zero files are uploaded to external servers.
- **ISO-BMFF Topology Inspector:** Parses top-level MP4/MOV atoms (`ftyp`, `moov`, `mdat`, `free`, `udta`) and detects video descriptors (`hvc1`, `hev1`, `avc1`, `av01`, `apch`) alongside HDR metadata boxes (`clli`, `mdcv`, `dvcC`).
- **Lossless FastStart & Tag Remuxing:**
  - Patches `hev1` descriptors to `hvc1` for hardware decoder compliance.
  - Relocates the `moov` atom ahead of `mdat` (**FastStart**) and recalculates 32-bit (`stco`) and 64-bit (`co64`) chunk offset tables.
  - Strips NLE software signature boxes (`udta`) that trigger aggressive server transcoding.
- **Broadcast Signal Diff Monitor:** Interactive 60FPS canvas monitor with 2X pixel loupe zoom comparing standard ~2.2 Mbps platform re-encoding against direct `hvc1` stream passthrough.

## Local Development
Open `index.html` directly in any modern desktop or mobile browser, or serve locally:

```bash
python -m http.server 8080
```

---

## Author
Built by **Harith**
- **Telegram:** [@harithwyd](https://t.me/harithwyd)
- **GitHub:** [XC0D3-X](https://github.com/XC0D3-X)
