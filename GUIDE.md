# Step-by-Step Guide

This guide walks through setting up n8n and running each of the four OSINT workflows.

## 1. Install n8n

Easiest path is Docker:

```bash
docker run -it --rm --name n8n -p 5678:5678 -v n8n_data:/home/node/.n8n docker.n8n.io/n8nio/n8n
```

Open `http://localhost:5678` and create your local n8n owner account on first launch.

## 2. Get your API keys

- **SerpAPI** — sign up at [serpapi.com](https://serpapi.com/), copy your key from the dashboard.
- **Hunter.io** — sign up at [hunter.io](https://hunter.io/), copy your key from account settings.
- **Groq** — sign up at [console.groq.com](https://console.groq.com/), generate a key under API Keys.

## 3. Import a workflow

1. In n8n, click **Workflows → Add workflow → Import from File**.
2. Pick one of the `.json` files from `n8n-workflows/Ex 1` .. `Ex 4`.
3. The workflow loads with nodes already wired up, but the API keys are placeholders.

## 4. Set your keys in the workflow

Each workflow has HTTP Request nodes calling SerpAPI / Hunter.io, and one or more Groq (chat model) nodes.

- Open each **HTTP Request** node that hits `serpapi.com` or `api.hunter.io` and replace `YOUR_SERPAPI_KEY` / `YOUR_HUNTER_IO_KEY` in the URL query string with your real key.
- Open the **Groq** node(s) and replace `YOUR_GROQ_API_KEY` in the Authorization header (or n8n credential, if you set one up) with your real key.

Prefer using n8n's built-in **Credentials** manager instead of pasting keys into node fields directly — create a credential once, then select it from each node's credential dropdown.

## 5. Run it

- **Ex 1 (OSINT)** and **Ex 2 (OSINT + Phishing)** start with a **Chat Trigger** node. Click **Chat** in the n8n canvas toolbar to open the built-in chat panel, then type something like:
  `do osint on John Smith from Acme Corp`
  The workflow parses the name/company, searches LinkedIn/X/Facebook/Instagram via SerpAPI, looks up the company domain via Hunter.io, and summarizes findings with Groq.
- **Ex 3 (Scan)** and **Ex 4 (All in One)** follow the same pattern — trigger via chat, inspect each node's output in the n8n execution panel to see the raw API responses and the final AI-generated summary.

## 6. Activate for repeated use (optional)

Toggle the workflow to **Active** (top-right switch) if you want its webhook/chat trigger to stay listening outside of manual test runs.

## Notes

- All the parsing logic (name/company extraction, domain guessing) lives in the **Code** nodes — open them to see or tweak the JavaScript.
- If a node errors out, check the n8n execution log first — most failures are an invalid/missing API key or a rate limit from the free tier of SerpAPI/Hunter.io.
