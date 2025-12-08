# The Big Brother v2.1 - "Quantum Eye"

## Overview

**The Big Brother** is an advanced OSINT reconnaissance tool for username enumeration across 473+ platforms with integrated visual intelligence capabilities.

---

## Core Capabilities

### Username Intelligence
- Automated scanning across 473 social media and web platforms
- Real-time profile discovery and validation
- CSV export for investigation documentation
- Advanced lookup via dorks integration

### Visual Intelligence
- Instant 3-image profile preview for identified accounts
- Quad-vector reverse image search 
- NSFW content support for comprehensive profiling
- Individual image download functionality

### Interface
- Real-time scan progress monitoring
- Target analysis visualization with biometric overlays
- Responsive design for desktop and mobile

---

## 📦 Installation

```bash
# Install dependencies
pip install -r requirements.txt
playwright install chromium

# Launch
python3 -m uvicorn the_big_brother.gui.main:app --port 8000
```

Open browser: `http://127.0.0.1:8000`

---

## 🔧 Configuration

### Scan Delays
Modify in `scanner.py`:
```python
time.sleep(0.5)  # Adjust delay between requests
```

### Image Limits
Modify in `image_grabber.py`:
```python
def fetch_images(query: str, limit: int = 3)  # Change limit
```

### NSFW Filtering
Already disabled by default. To re-enable SafeSearch:
```python
# image_grabber.py
page.goto(f"...&safe=active")  # Change from safe=off

# reverse_search.py
url = f"...&safe=active"  # Change from safe=off
```

---

## 📊 Technical Specifications

### Architecture
- **Backend**: FastAPI (async)
- **Frontend**: Vanilla JS + CSS (no frameworks)
- **Browser Automation**: Playwright (Chromium)
- **Concurrency**: asyncio.gather() for parallel execution

### Performance
- **Initial Image Fetch**: ~3-5 seconds
- **Deep Search**: ~15-25 seconds (4 engines in parallel)
- **Site Scan**: ~2-5 minutes (473 sites)

### Browser Compatibility
- Chrome/Chromium ✅
- Firefox ✅
- Safari ✅
- Edge ✅

---

## 🤝 Contributing

Contributions welcome! Submit pull requests with detailed descriptions.

---

## � Support

- **GitHub**: [@chadi0x](https://github.com/chadi0x)
- **Issues**: Report bugs via GitHub Issues
- **Custom Solutions**: Contact for enterprise licensing

---

---

## � Premium Version Available

**Looking for more power?** A custom-built enterprise version is available with advanced capabilities:
- **Real-time phone tracking** (educational purposes only)
- **Enhanced facial recognition**
- **Automated report generation**
- **API access for integration**
- **Priority support**

*Contact for custom solutions and enterprise licensing.*

---

## 📜 Disclaimer

This tool is provided for **educational and research purposes only**. Users are responsible for ensuring their use complies with applicable laws and regulations. The author assumes no liability for misuse.

---

> *"In the digital age, anonymity is a luxury. Information is the currency of power."*  
> — **CHADI0X**

**More projects coming soon. Stay ready.** 🚀

---

**Built by CHADI0X** | **Quantum OSINT Engine v2.1**
