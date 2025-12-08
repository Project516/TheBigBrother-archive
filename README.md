# 👁️ THE BIG BROTHER v2.1

```
╔══════════════════════════════════════════════════════════════╗
║                                                              ║
║   ████████╗██╗  ██╗███████╗    ██████╗ ██╗ ██████╗         ║
║   ╚══██╔══╝██║  ██║██╔════╝    ██╔══██╗██║██╔════╝         ║
║      ██║   ███████║█████╗      ██████╔╝██║██║  ███╗        ║
║      ██║   ██╔══██║██╔══╝      ██╔══██╗██║██║   ██║        ║
║      ██║   ██║  ██║███████╗    ██████╔╝██║╚██████╔╝        ║
║      ╚═╝   ╚═╝  ╚═╝╚══════╝    ╚═════╝ ╚═╝ ╚═════╝         ║
║                                                              ║
║   ██████╗ ██████╗  ██████╗ ████████╗██╗  ██╗███████╗██████╗ ║
║   ██╔══██╗██╔══██╗██╔═══██╗╚══██╔══╝██║  ██║██╔════╝██╔══██╗║
║   ██████╔╝██████╔╝██║   ██║   ██║   ███████║█████╗  ██████╔╝║
║   ██╔══██╗██╔══██╗██║   ██║   ██║   ██╔══██║██╔══╝  ██╔══██╗║
║   ██████╔╝██║  ██║╚██████╔╝   ██║   ██║  ██║███████╗██║  ██║║
║   ╚═════╝ ╚═╝  ╚═╝ ╚═════╝    ╚═╝   ╚═╝  ╚═╝╚══════╝╚═╝  ╚═╝║
║                                                              ║
║              QUANTUM OSINT RECONNAISSANCE ENGINE             ║
║                      Version 2.1.0                           ║
╚══════════════════════════════════════════════════════════════╝
```

<div align="center">

**Advanced OSINT Tool for Username Intelligence & Visual Reconnaissance**

[![Version](https://img.shields.io/badge/version-2.1.0-00ff41.svg)](https://github.com/chadi0x/the-big-brother/releases)
[![License](https://img.shields.io/badge/license-MIT-00ff41.svg)](LICENSE)
[![Python](https://img.shields.io/badge/python-3.9+-00ff41.svg)](https://www.python.org/)
[![Status](https://img.shields.io/badge/status-active-00ff41.svg)]()

[Features](#-features) • [Installation](#-installation) • [Usage](#-usage) • [Screenshots](#-screenshots) • [Support](#-support)

</div>

---

## 🎯 Overview

**The Big Brother** is a next-generation OSINT reconnaissance platform combining username enumeration across **473+ platforms** with advanced **quad-vector visual intelligence** capabilities.

### What It Does
- 🔍 **Username Discovery**: Scan 473+ social media and web platforms
- 🖼️ **Visual Intelligence**: 3-image profile preview + reverse image search
- 🎯 **Deep Search**: Quad-vector engine (Google, Bing, Yandex, TinEye)
- 📊 **Export Reports**: CSV format for documentation

---

## ⚡ Features

### Core Capabilities

```
┌─────────────────────────────────────────────────────────┐
│ USERNAME INTELLIGENCE                                   │
├─────────────────────────────────────────────────────────┤
│ ✓ 473+ Platform Coverage                                │
│ ✓ Real-time Profile Discovery                           │
│ ✓ Advanced Lookup via Dorks                             │
│ ✓ CSV Export                                            │
└─────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────┐
│ VISUAL INTELLIGENCE                                     │
├─────────────────────────────────────────────────────────┤
│ ✓ Instant 3-Image Preview                               │
│ ✓ Quad-Vector Reverse Search                            │
│ ✓ NSFW Content Support                                  │
│ ✓ Individual Image Download                             │
└─────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────┐
│ INTERFACE                                               │
├─────────────────────────────────────────────────────────┤
│ ✓ Real-time Progress Monitoring                         │
│ ✓ Target Analysis Visualization                         │
│ ✓ Responsive Design                                     │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

---

## 🚀 Installation

### Quick Setup

```bash
# 1. Install dependencies
pip install -r requirements.txt

# 2. Install browser
playwright install chromium

# 3. Launch
python3 -m uvicorn the_big_brother.gui.main:app --port 8000
```

**Access**: Open browser to `http://127.0.0.1:8000`

> See [SETUP.md](SETUP.md) for detailed installation on Windows, macOS, and Linux

---

## 🎨 Interface

### Main Dashboard
- **Search Bar**: Enter target username
- **INITIATE Button**: Start reconnaissance scan
- **Platform Selector**: Choose advanced lookup platform
- **Results Grid**: Displays discovered profiles with images

### Image Intelligence
- **3-Image Preview**: Automatic profile image fetch
- **DEEP SEARCH Button**: Hover over images to reveal
- **Download Icons**: Individual image download

### Deep Visual Intel Modal
- **Target Analysis Center**: Selected image with scanning overlay
- **Quad-Vector Grid**: 2x2 layout showing results from:
  - Google Images (top-left)
  - Bing Visual (top-right)
  - Yandex Vision (bottom-left)
  - TinEye Tracker (bottom-right)
- **Status Bar**: Real-time search progress

### Controls
- **ABORT SEQUENCE**: Stop active scan
- **EXPORT DATA**: Download CSV report
- **Platform Dorks**: Execute advanced search queries

---

## 📖 Usage

### Basic Workflow

```
1. Enter Username → 2. Click INITIATE → 3. View Results
```

### Deep Search

```
Click Image → View Quad-Vector Results → Download
```

### Export

```
Complete Scan → Click EXPORT DATA → Download CSV
```

---

## 📸 Screenshots

><img width="1658" height="843" alt="Screenshot 2025-12-07 at 18 19 35" src="https://github.com/user-attachments/assets/183608e2-daa7-4f2a-bfd4-ef80b4c7518e" />


---

## 💎 Premium Version

**Looking for advanced capabilities?**

Custom enterprise version available with:
- Real-time phone tracking (educational purposes)
- Enhanced facial recognition
- Automated reporting
- API integration
- Priority support

*Contact for custom solutions*
Telegram : Hisoka0morow

## ⚠️ Disclaimer

This tool is for **educational and research purposes only**. Users are responsible for compliance with applicable laws. The author assumes no liability for misuse.

---

## 📞 Support

- **GitHub**: [@chadi0x](https://github.com/chadi0x)
- **Issues**: [Report Bugs](https://github.com/chadi0x/the-big-brother/issues)
- **Custom Solutions**: Contact for enterprise licensing

---

## 📜 License

MIT License - See [LICENSE](LICENSE)

---

<div align="center">

> *"In the digital age, anonymity is a luxury. Information is the currency of power."*  
> — **CHADI0X**

**More projects coming soon. Stay ready.** 🚀

---

**Built by CHADI0X** | **Quantum OSINT Engine v2.1**

</div>
