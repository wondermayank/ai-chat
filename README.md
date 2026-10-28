# ThunderAI — ThunderStudy Chat Assistant

AI-powered study assistant for CUET, Banking & Commerce students.
Built with Cloudflare Pages Functions.

## AI models (pick from the chat box)

| Name in chat | Notes |
| **Tiny** (default, Best) | Highest quality answers |
| Tiny Lite | Fast and smart |
| bytes | Balanced |
| bytes | Instant, simple doubts |

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
