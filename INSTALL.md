# How to Build and Run "The Big Brother"

## Prerequisites
- Python 3.9+
- Pip
- Git

## Installation Steps

1. **Clone the Repository**
   ```bash
   git clone <repository-url>
   cd the_big_brother
   ```

2. **Install Python Dependencies**
   Run the following command to install the package and required libraries:
   ```bash
   pip3 install .
   pip3 install fastapi uvicorn playwright duckduckgo-search
   ```

3. **Install Browser for Validation**
   This downloads the browser binaries needed for the headless validator:
   ```bash
   playwright install chromium
   ```

## Running the Tool

### Option 1: GUI (Recommended)
This launches the Hacker Themed Web Interface.

1. Start the server:
   ```bash
   uvicorn the_big_brother.gui.main:app --reload
   ```
2. Open your browser to:
   **http://127.0.0.1:8000**

3. Enter a username to scan. 
   - **Images**: The tool will grab 3 images associated with the username from search engines.
   - **Stop**: You can stop the scan at any time.
   - **Download**: Once finished (or stopped), download a CSV report.

### Option 2: CLI
For quick terminal scans:

```bash
python3 -m the_big_brother <username>
```

## Troubleshooting
- **Playwright Errors**: If validation fails, ensure you ran `playwright install`.
- **404 Errors**: Ensure you are in the root `the_big_brother` directory when running commands.
