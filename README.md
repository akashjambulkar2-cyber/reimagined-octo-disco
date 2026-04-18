# testPDF

A small collection of single-file, zero-dependency HTML apps. Each file is fully self-contained — open it in a browser and it runs. No build step, no server.

## Apps

### [apps/log-anomaly-analyzer.html](apps/log-anomaly-analyzer.html)

Browser-based log triage tool that uses the Anthropic Claude API to detect anomalies, suspicious patterns, and incidents in raw log output. Supports system, auth, network, application, audit, and mixed logs.

**Features**
- Six log-type tabs with built-in realistic sample logs (SSH brute force, SQL injection, data exfiltration, OOM kills, audit tampering, etc.)
- Sensitivity dial (standard / moderate / high), timezone, known-safe IPs, and known admin accounts passed into the prompt
- Executive summary, incident timeline visualization, anomaly findings table with severity badges, IP intelligence panel with click-to-filter, and a 5-section narrative report
- Output toolbar: **Copy Report** (plain text), **Download JSON**, **Download HTML Report** (printable, page-break-aware), **Analyze New Log**, **Share Summary** (modal with short email/Slack-ready text)
- Mobile-responsive, accessible (focus-visible outlines, severity icon+text, aria labels), print-friendly

**How to run**
1. Open [apps/log-anomaly-analyzer.html](apps/log-anomaly-analyzer.html) in any modern browser
2. Click the `🔑 API Key` button in the header and paste an Anthropic API key (get one at [console.anthropic.com](https://console.anthropic.com/))
3. Paste a log (or click `📂 Load Sample Log`) and hit `🔍 Analyze Logs`

**API key handling**
The key is stored in `localStorage` under the name `laa_api_key` — it never leaves your browser except in the direct API call to Anthropic. There are no hardcoded keys in this repo. If you fork this, your users bring their own key.

**Model**: `claude-sonnet-4-20250514` · `temperature: 0` · `max_tokens: 4000`

### [apps/notepad.html](apps/notepad.html)

Minimal in-browser notepad.

## Project structure

```
.
├── .github/
│   └── copilot-instructions.md
├── .gitattributes
├── .gitignore
├── README.md
└── apps/
    ├── log-anomaly-analyzer.html
    └── notepad.html
```

## License

No license specified — add one if you intend to accept contributions or publish.
