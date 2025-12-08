# Installation Guide

## Requirements
- Python 3.9 or higher
- Internet connection

---

## Windows

### 1. Install Python
Download from [python.org](https://www.python.org/downloads/) and install.

### 2. Install Dependencies
```cmd
pip install -r requirements.txt
playwright install chromium
```

### 3. Launch
```cmd
python -m uvicorn the_big_brother.gui.main:app --port 8000
```

### 4. Access
Open browser: `http://127.0.0.1:8000`

---

## macOS

### 1. Install Python (if not installed)
```bash
brew install python@3.9
```

### 2. Install Dependencies
```bash
pip3 install -r requirements.txt
playwright install chromium
```

### 3. Launch
```bash
python3 -m uvicorn the_big_brother.gui.main:app --port 8000
```

### 4. Access
Open browser: `http://127.0.0.1:8000`

---

## Linux

### 1. Install Python (if not installed)
```bash
# Ubuntu/Debian
sudo apt update
sudo apt install python3 python3-pip

# Fedora/RHEL
sudo dnf install python3 python3-pip
```

### 2. Install Dependencies
```bash
pip3 install -r requirements.txt
playwright install chromium
```

### 3. Launch
```bash
python3 -m uvicorn the_big_brother.gui.main:app --port 8000
```

### 4. Access
Open browser: `http://127.0.0.1:8000`

---

## Troubleshooting

**Port already in use:**
```bash
# Use different port
python3 -m uvicorn the_big_brother.gui.main:app --port 8080
```

**Playwright issues:**
```bash
# Reinstall browsers
playwright install chromium --force
```

**Permission errors (Linux/macOS):**
```bash
# Use --user flag
pip3 install -r requirements.txt --user
```


## Quick Setup (5 Minutes)

### 1. Prerequisites
```bash
# Check Python version (3.9+ required)
python3 --version

# Install pip if not available
python3 -m ensurepip --upgrade
```

### 2. Clone & Install
```bash
# Navigate to project directory
cd the_big_brother_v2.1

# Install in development mode
pip install -e .

# Install Playwright browsers (CRITICAL)
playwright install chromium
```

### 3. Launch Application
```bash
# Start the GUI server
python3 -m uvicorn the_big_brother.gui.main:app --reload --port 8000 --host 127.0.0.1

# Open in browser
# Navigate to: http://127.0.0.1:8000
```

---

## Detailed Installation

### System Requirements
- **OS**: macOS, Linux, Windows (WSL recommended)
- **Python**: 3.9, 3.10, 3.11, or 3.12
- **RAM**: 2GB minimum (4GB recommended)
- **Disk**: 500MB for dependencies + browsers

### Dependencies
All dependencies are managed via `pyproject.toml`:
- **FastAPI**: Web framework
- **Playwright**: Browser automation
- **Uvicorn**: ASGI server
- **Requests**: HTTP library
- **BeautifulSoup4**: HTML parsing

### Installation Methods

#### Method 1: pip install (Recommended)
```bash
cd the_big_brother_v2.1
pip install -e .
playwright install chromium
```

#### Method 2: Poetry
```bash
cd the_big_brother_v2.1
poetry install
poetry run playwright install chromium
```

#### Method 3: Docker
```bash
cd the_big_brother_v2.1
docker build -t the-big-brother:2.1 .
docker run -p 8000:8000 the-big-brother:2.1
```

---

## Configuration

### Port Configuration
Default port is 8000. To change:
```bash
python3 -m uvicorn the_big_brother.gui.main:app --port 8080
```

### Scan Delays
Edit `the_big_brother/scanner.py`:
```python
time.sleep(0.5)  # Adjust delay between site checks
```

### Image Fetch Limits
Edit `the_big_brother/image_grabber.py`:
```python
def fetch_images(query: str, limit: int = 3)  # Change to 5, 10, etc.
```

### NSFW Content
Already enabled by default. To disable:
```python
# In image_grabber.py and reverse_search.py
# Change: &safe=off → &safe=active
# Change: &adlt=off → &adlt=moderate
```

---

## Troubleshooting

### Issue: "Playwright not found"
```bash
# Reinstall Playwright browsers
playwright install chromium

# If still failing, install system dependencies
playwright install-deps
```

### Issue: "Port already in use"
```bash
# Find process using port 8000
lsof -i :8000

# Kill the process
kill -9 <PID>

# Or use a different port
python3 -m uvicorn the_big_brother.gui.main:app --port 8080
```

### Issue: "No images showing"
- Check internet connection
- Verify Playwright is installed: `playwright --version`
- Check browser console for errors (F12)
- Try different username (some profiles have no images)

### Issue: "Deep Search fails"
- Wait 30 seconds (engines need time)
- Check if image URL is publicly accessible
- Some engines may be geo-blocked (normal behavior)
- At least 1-2 engines should always work

---

## Usage Examples

### Basic Username Scan
```
1. Enter username: "johndoe"
2. Click "INITIATE"
3. Wait for results (2-5 minutes)
4. View found profiles + images
```

### Deep Visual Intel
```
1. Complete basic scan first
2. Click any profile image
3. Watch "Target Analysis" animation
4. View results from 4 engines
5. Download similar images
```

### Google Dorks
```
1. Select platform (e.g., "LinkedIn")
2. Click "DEPLOY DORKS"
3. Opens Google with advanced search
```

### Export Results
```
1. Complete scan
2. Click "EXPORT DATA"
3. Downloads CSV report
```

---

## Production Deployment

### Systemd Service (Linux)
Create `/etc/systemd/system/bigbrother.service`:
```ini
[Unit]
Description=The Big Brother OSINT Tool
After=network.target

[Service]
Type=simple
User=www-data
WorkingDirectory=/opt/the_big_brother_v2.1
ExecStart=/usr/bin/python3 -m uvicorn the_big_brother.gui.main:app --host 0.0.0.0 --port 8000
Restart=always

[Install]
WantedBy=multi-user.target
```

Enable and start:
```bash
sudo systemctl enable bigbrother
sudo systemctl start bigbrother
```

### Nginx Reverse Proxy
```nginx
server {
    listen 80;
    server_name osint.example.com;

    location / {
        proxy_pass http://127.0.0.1:8000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
    }
}
```

### Docker Compose
```yaml
version: '3.8'
services:
  bigbrother:
    build: .
    ports:
      - "8000:8000"
    restart: unless-stopped
```

---

## Security Considerations

### Network Security
- **Do NOT expose to public internet without authentication**
- Use VPN or SSH tunnel for remote access
- Consider adding basic auth via Nginx

### Rate Limiting
- Built-in delays prevent most rate limits
- For heavy usage, consider rotating proxies
- Respect target site ToS

### Data Privacy
- No data is stored permanently (in-memory only)
- Clear browser on exit
- Use incognito/private browsing when possible

---

## Performance Tuning

### Faster Scans
```python
# Reduce delay in scanner.py
time.sleep(0.2)  # From 0.5

# Increase concurrent requests (risky)
# Not recommended - may trigger rate limits
```

### More Images
```python
# In image_grabber.py
def fetch_images(query: str, limit: int = 10)  # From 3
```

### Headless vs Headed
```python
# In reverse_search.py
ReverseImageSearcher(headless=False)  # Show browser (debugging)
```

---

## Updating

### From v2.0 to v2.1
```bash
cd the_big_brother_v2.1
git pull origin main
pip install -e . --upgrade
playwright install chromium --force
```

### Checking Current Version
```bash
cat VERSION
# or
python3 -c "import the_big_brother; print(the_big_brother.__version__)"
```

---

## Support & Community

- **GitHub Issues**: Bug reports and feature requests
- **Discussions**: General questions and tips
- **Wiki**: Extended documentation (coming soon)

---

**Ready to Deploy!** 🚀

For questions, open an issue on GitHub or check the [RELEASE.md](RELEASE.md) for detailed feature documentation.
