# OSINT AI Workflows

n8n workflow automations for AI-assisted OSINT (Open Source Intelligence) reconnaissance, built as part of a cyber operations course.

## Exercises

- **Ex 1 — OSINT**: Automated target lookup across LinkedIn, X/Twitter, Facebook, Instagram (via SerpAPI) with AI-powered analysis (Groq).
- **Ex 2 — OSINT + Phishing**: Extends Ex 1 with company/domain lookup (Hunter.io) for phishing simulation prep.
- **Ex 3 — Scan**: Network/recon scanning workflow.
- **Ex 4 — All in One**: Combined end-to-end OSINT + phishing + scan pipeline.

## Prerequisites

- Docker installed
- [n8n](https://n8n.io/) (self-hosted or cloud)
- API keys for:
  - [SerpAPI](https://serpapi.com/) — Google/LinkedIn/X/Facebook/Instagram search
  - [Hunter.io](https://hunter.io/) — email & company lookup
  - [Groq](https://groq.com/) — AI analysis

## Setup

1. Import the desired `.json` workflow into n8n.
2. Replace the placeholder values in the workflow (`YOUR_SERPAPI_KEY`, `YOUR_HUNTER_IO_KEY`, `YOUR_GROQ_API_KEY`) with your own API keys — either directly in the HTTP Request nodes or, preferably, via n8n credentials.
3. Activate the workflow and trigger it via the chat trigger node.

## Disclaimer

For authorized security research, red-teaming, and educational use only. Do not use against targets without explicit authorization.
