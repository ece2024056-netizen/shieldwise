Shieldwise AI

Shieldwise AI is a local-first assistant for normal conversations, financial education, and scam-safety support. It runs through Ollama and includes persistent chat history plus finance-specific visual explainers.

> Shieldwise provides educational information only. It is not a bank, broker, investment adviser, tax adviser, or legal service.

## Features

- General-purpose local AI chat
- Finance-aware responses for scams, budgeting, debt, investing, and banking topics
- Structured financial responses: assessment, risks, next steps, and items to verify
- Local conversation history stored in the browser
- Finance-only infographic generation with a local AI SVG generator and diagram fallback
- Formal, accessible chat interface
- Server-side AI proxy that avoids browser CORS failures

## Requirements

- Node.js 18 or newer
- Ollama installed and running locally
- A compatible local model, such as `gemma3:1b`

Install the default model:

```bash
ollama pull gemma3:1b
```

## Run locally

Start the web server:

```bash
node server.mjs
```

Then open [http://localhost:8787](http://localhost:8787).

On Windows, you can run `Start Shieldwise.cmd` instead. Keep its terminal window open while using the app.

## Configuration

The local defaults are:

```text
OLLAMA_URL=http://127.0.0.1:11434/api/chat
OLLAMA_MODEL=gemma3:1b
```

Copy `.env.example` as a reference when configuring another environment. The Node server reads environment variables supplied by your hosting platform; it does not load secrets from the browser.

## Public deployment

This project cannot run as an AI application on GitHub Pages alone because GitHub Pages cannot run `server.mjs` or host an AI model.

Deploy it to a Node-capable host and set:

```text
OLLAMA_URL=https://your-private-ollama-host/api/chat
OLLAMA_MODEL=gemma3:1b
```

Keep the AI endpoint private or place it behind an authenticated gateway. Never expose an unauthenticated Ollama endpoint directly to the internet.

See [PUBLIC_DEPLOYMENT.md](PUBLIC_DEPLOYMENT.md) for the full deployment checklist.

## Security and safety

- Do not submit OTPs, PINs, passwords, account numbers, or full card details.
- Verify time-sensitive financial information through official sources before acting.
- For suspected financial fraud in India, contact your bank through official channels and report promptly through the national cybercrime channels.
- Do not treat generated visual explainers as professional financial advice.

## License

This project is available under the [MIT License](LICENSE).
