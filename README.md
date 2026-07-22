<div align="center">

# 🕵️ OSINT AI Workflows

### AI-powered OSINT recon, phishing prep & network scanning — automated with n8n

[![n8n](https://img.shields.io/badge/n8n-workflow-EA4B71?style=for-the-badge&logo=n8n&logoColor=white)](https://n8n.io/)
[![Groq](https://img.shields.io/badge/AI-Groq-F55036?style=for-the-badge)](https://groq.com/)
[![License](https://img.shields.io/badge/license-Educational%20Use-blue?style=for-the-badge)](#disclaimer)
[![Status](https://img.shields.io/badge/status-active-success?style=for-the-badge)]()

![GitHub repo size](https://img.shields.io/github/repo-size/Yaman-RedTeam/osint-ai-workflows?style=flat-square&color=orange)
![GitHub last commit](https://img.shields.io/github/last-commit/Yaman-RedTeam/osint-ai-workflows?style=flat-square&color=blueviolet)
![GitHub stars](https://img.shields.io/github/stars/Yaman-RedTeam/osint-ai-workflows?style=flat-square&color=yellow)

</div>

---

## 📖 Overview

A set of **n8n** automation workflows that chain AI (Groq) with OSINT data sources (SerpAPI, Hunter.io) to automate reconnaissance, phishing-prep, and scanning tasks for authorized red-team / security research engagements.

## 🧩 Exercises

| # | Workflow | Description |
|---|----------|-------------|
| **Ex 1** | 🔍 OSINT | Automated target lookup across LinkedIn, X/Twitter, Facebook, Instagram (via SerpAPI) with AI-powered analysis (Groq) |
| **Ex 2** | 🎣 OSINT + Phishing | Extends Ex 1 with company/domain lookup (Hunter.io) for phishing simulation prep |
| **Ex 3** | 📡 Scan | Network / recon scanning workflow |
| **Ex 4** | 🧠 All in One | Combined end-to-end OSINT + phishing + scan pipeline |

## ⚙️ Prerequisites

- 🐳 Docker installed
- [n8n](https://n8n.io/) (self-hosted or cloud)
- 🔑 API keys for:
  - [SerpAPI](https://serpapi.com/) — Google / LinkedIn / X / Facebook / Instagram search
  - [Hunter.io](https://hunter.io/) — email & company lookup
  - [Groq](https://groq.com/) — AI analysis

## 🚀 Setup

> 📘 New here? See the full walkthrough in [GUIDE.md](./GUIDE.md).

1. Import the desired `.json` workflow into n8n.
2. Replace the placeholder values (`YOUR_SERPAPI_KEY`, `YOUR_HUNTER_IO_KEY`, `YOUR_GROQ_API_KEY`) with your own API keys — either directly in the HTTP Request nodes or, preferably, via n8n credentials.
3. Activate the workflow and trigger it via the chat trigger node.

## 📁 Structure

```
n8n-workflows/
├── Ex 1/   → OSINT
├── Ex 2/   → OSINT + Phishing
├── Ex 3/   → Scan
└── Ex 4/   → All in One
```

## ⚠️ Disclaimer

> For **authorized security research, red-teaming, and educational use only**. Do not use against targets without explicit authorization.

---

<div align="center">

Made with 🧠 + 🤖 for OSINT automation

</div>
