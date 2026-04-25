# ResearchMind AI 🔬

A Telegram bot that researches any topic in real time using live web search and Groq AI. Ask it anything — it fetches current data from the web and gives you a straight, concise answer in your language.

Built entirely on free-tier tools with n8n Cloud.

---

## How It Works

You send a message to the Telegram bot → it searches the web live via SerpAPI → feeds the results into Groq Llama 3.3 70B → sends back a clean, direct answer. No fluff.

```
Telegram → Parse Message → SerpAPI Search → Build Context → Groq AI → Telegram
```

---

## Features

- 🔎 Live web search on every query
- 🌍 Auto-detects and responds in your language
- ⚡ Powered by Llama 3.3 70B via Groq
- 📩 Delivered straight to Telegram
- 💡 Every answer ends with a key takeaway

---

## Tech Stack

| Tool | Purpose | Cost |
|------|---------|------|
| n8n Cloud | Workflow automation | Free |
| Telegram Bot API | Chat interface | Free |
| SerpAPI | Live Google search | Free (100/month) |
| Groq API | LLM inference | Free |
| Llama 3.3 70B | AI model | Free |

---

## Setup

**1. Clone this repo**
```bash
git clone https://github.com/Ikechukwu50/researchmind-ai.git
```

**2. Get your API keys**
- Telegram Bot Token → [@BotFather](https://t.me/BotFather)
- SerpAPI Key → [serpapi.com](https://serpapi.com)
- Groq API Key → [console.groq.com](https://console.groq.com)

**3. Import the workflow**
- Open n8n Cloud
- New Workflow → Import from File → select `researchmind-ai.json`

**4. Add credentials**
- Telegram API → paste your Bot Token
- SerpAPI → paste key in the Google Search node
- Groq → create a Header Auth credential with `Authorization: Bearer YOUR_KEY`

**5. Publish and test**
- Hit Publish in n8n
- Open your Telegram bot and send any question

---

## Workflow Nodes

| Node | Type | What It Does |
|------|------|-------------|
| Telegram Trigger | Built-in | Receives user messages |
| Parse Message | Code (JS) | Extracts query, chatId, language |
| Google Search | SerpAPI | Fetches top 5 live results |
| Build Research Context | Code (JS) | Formats results for AI |
| AI Agent | Groq Llama 3.3 | Generates concise answer |
| Send Result | Telegram | Delivers answer to user |

---

## Example

```
User: which coin is ranking 7th on coingecko

Bot: SOL (Solana) is ranking 7th on CoinGecko.
     💡 Solana remains one of the top layer-1 blockchains by market cap.
```

```
User: qui est le président de la France

Bot: Emmanuel Macron est le président de la France depuis 2017.
     💡 Il a été réélu pour un second mandat en 2022.
```

---

## Project Stats

- 6 nodes total
- $0 monthly cost
- ~4 second average response
- 10+ languages supported

---

## Author

Built by [Ikechukwu Miller](https://github.com/Ikechukwu50) — AI & Automation Engineer specializing in fintech, crypto, and workflow automation.
