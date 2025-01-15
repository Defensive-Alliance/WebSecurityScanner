# WebSecurityScanner

A Python-based tool to scan websites for common vulnerabilities like SQL Injection, Cross-Site Scripting (XSS), and sensitive information exposure. This scanner helps you identify security risks in web applications by crawling the website and testing for specific vulnerabilities.

## Features
- **SQL Injection Detection**: Identifies potential SQL injection vulnerabilities by testing URL parameters.
- **Cross-Site Scripting (XSS) Detection**: Detects vulnerabilities that allow injection of malicious JavaScript into web pages.
- **Sensitive Information Exposure**: Scans for sensitive data, such as email addresses, phone numbers, and API keys exposed in web responses.

## Requirements

Ensure you have the following installed:

- Python 3.x
- `pip` (Python package installer)

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/Defensive-Alliance/web-security-scanner.git
cd web-security-scanner
```

### 2. Install Dependencies

Install the required Python packages using the following command:

```bash
pip install -r requirements.txt
```

The scanner depends on the following libraries:
- `requests`: For sending HTTP requests.
- `beautifulsoup4`: For parsing HTML and extracting links.
- `urllib3`: For URL parsing and management.
- `colorama`: For colored output in the terminal.

## Usage

After setting up the environment, you can run the scanner using the following command:

### Run the Scanner

```bash
python webscanner.py <target_url>
```

Replace `<target_url>` with the URL of the website you wish to scan. For example:

```bash
python webscanner.py https://example.com
```

### Sample Output

Once the scan is complete, the vulnerabilities found will be displayed in the terminal:

```bash
[VULNERABILITY FOUND]
type: SQL Injection
url: https://example.com/page
parameter: id
payload: ' OR 1=1--

[VULNERABILITY FOUND]
type: Cross-Site Scripting (XSS)
url: https://example.com/login
parameter: username
payload: <script>alert('XSS')</script>

[VULNERABILITY FOUND]
type: Sensitive Information Exposure
url: https://example.com/secret
info_type: email
pattern: [a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}
```

## How It Works

1. **Crawling**: The scanner starts by crawling the target website and collecting all the accessible pages and URLs within the domain.
2. **Testing for Vulnerabilities**:
   - **SQL Injection**: It attempts to inject common SQL payloads into URL parameters and checks for SQL errors in the response.
   - **XSS (Cross-Site Scripting)**: It injects common XSS payloads into URL parameters and checks if the payload is reflected in the response.
   - **Sensitive Information Exposure**: It checks if sensitive data like emails, phone numbers, or API keys are exposed in the page content.


## Contributing

We welcome contributions! If you find a bug, have a feature request, or want to improve the project, please fork the repository and submit a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
```

This version provides a simple and clean overview of the scanner, explaining its functionality, how to use it, and how others can extend or contribute to it. Let me know if you need any more changes!
