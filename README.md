# ThunderAI — ThunderStudy Chat Assistant

AI-powered study assistant for CUET, Banking & Commerce students.
Built with Groq + Cloudflare Pages Functions.

## AI models (pick from the chat box)

| Name in chat | Groq model | Notes |
|---|---|---|
| **Tiny** (default, Best) | `openai/gpt-oss-120b` | Highest quality answers |
| Tiny Lite | `openai/gpt-oss-20b` | Fast and smart |
| Llama 3.3 70B | `llama-3.3-70b-versatile` | Balanced |
| Llama 3.1 8B | `llama-3.1-8b-instant` | Instant, simple doubts |

The choice is remembered in the browser. If the chosen model is unavailable for your Groq key,
the server automatically tries the others (Tiny first) and the chat shows which one answered.
Open `/api/chat` to see the live model list. To rename or reorder models, edit `MODELS` in
`functions/api/chat.js` and `index.html` (keys must match).

---

## Folder Structure
```
thunderai/
├── index.html       ← Frontend chat UI
├── vercel.json      ← Vercel config
└── api/
    └── chat.js      ← Serverless API (Groq proxy)
---

Made by Wondermayank — https://wondermayank.github.io
