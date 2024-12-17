# Security Scanner 🔍

A Python-based **Web Security Scanner** for detecting vulnerabilities such as **SQL Injections**, **Cross-Site Scripting (XSS)**, and **Sensitive Information Disclosure** on a given target URL.

---

## Features 🚀

- **Crawls websites** to discover pages and endpoints up to a configurable depth.
- Detects common web vulnerabilities:
  - **SQL Injections**
  - **Cross-Site Scripting (XSS)**
  - **Sensitive Information Disclosure** (emails, phone numbers, API keys, etc.).
- Multi-threaded scanning for faster results.
- Generates detailed vulnerability reports.

---

## Prerequisites ⚙️

Before running this script, ensure you have the following:

- **Python 3.7+** installed.
- Required dependencies installed via `pip`.

---

## Installation 👅

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/security-scanner.git
   cd security-scanner
   ```

2. Install the required libraries:
   ```bash
   pip install -r requirements.txt
   ```

**Dependencies**:
- `requests` for HTTP requests
- `BeautifulSoup4` for HTML parsing
- `colorama` for colored CLI output

---

## Usage 🛠️

Run the script with a target URL:

```bash
python scanner.py <target_url>
```

### Example:
```bash
python scanner.py https://example.com
```

---

## How It Works 🧠

1. **Crawling**:
   - The script starts by crawling the target website to discover all linked pages.
   - You can configure the crawl depth (default is `3`).

2. **Vulnerability Scanning**:
   - **SQL Injection**: Attempts common SQL payloads to identify vulnerabilities.
   - **XSS**: Tests for cross-site scripting using a variety of payloads.
   - **Sensitive Info**: Searches for sensitive patterns like emails, phone numbers, SSNs, or API keys.

3. **Reporting**:
   - Found vulnerabilities are printed in real time with details:
     - **Type**: Type of vulnerability (e.g., SQL Injection, XSS).
     - **URL**: Affected URL.
     - **Parameter**: The vulnerable parameter.
     - **Payload**: Payload that triggered the vulnerability.

---

## Output Example 📃

```plaintext
Starting security scan of https://example.com

[VULNERABILITY FOUND]
type: SQL Injection
url: https://example.com/search?q=1' OR '1'='1
parameter: q
payload: 1' OR '1'='1

[VULNERABILITY FOUND]
type: Cross-Site-Scripting
url: https://example.com/comment?msg=<script>alert('XSS')</script>
parameter: msg
payload: <script>alert('XSS')</script>

Scan Complete!
Total URLs scanned: 5
Vulnerabilities found: 2
```

---

## Configuration ⚙️

- Modify the **`max_depth`** in `Security_Scanner` to control how deep the crawler explores the website.
- Add more payloads for testing in:
  - `check_sql_injections()` for SQL payloads.
  - `check_for_xss()` for XSS payloads.
  - `check_for_sensitive_info()` for additional sensitive patterns.

---

## Disclaimer ⚠️

This tool is intended for **educational purposes** and for testing on websites that **you own** or have explicit permission to scan. Unauthorized use of this tool on third-party systems is **illegal** and unethical.

---

## Contributing 🤝

Feel free to submit issues or pull requests to improve the tool.

---

## License 📜

This project is licensed under the **MIT License**.

---

