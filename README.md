# ThunderAI — Cloudflare Worker

AI study mentor for ThunderStudy. Runs fully on Cloudflare Workers — no Vercel, no CORS issues.

**Live URL:** https://ai.thunderstudy.indevs.in/chat

## Stack
- **Runtime:** Cloudflare Workers
- **AI:** Groq API (llama-3.3-70b-versatile)
- **Frontend:** Single-file HTML served by the worker at `/chat`
- **API:** Worker handles `/api/chat` on the same domain → no CORS ever

## Deploy (first time)

### 1. Install Wrangler
```bash
npm install
```

### 2. Login to Cloudflare
```bash
npx wrangler login
```

### 3. Add your Groq API key as a secret
```bash
npx wrangler secret put GROQ_API_KEY
# paste your key when prompted
```

### 4. Deploy
```bash
npm run deploy
```

### 5. Add custom domain in Cloudflare Dashboard
- Go to Workers & Pages → thunderai → Settings → Triggers
- Add Custom Domain: `ai.thunderstudy.indevs.in`
- The worker will handle `/chat` and `/api/chat` automatically

## Local dev
```bash
npm run dev
# opens at http://localhost:8787/chat
```
Add a `.dev.vars` file for local secrets:
```
GROQ_API_KEY=your_key_here
```

## File structure
```
thunderai-cf/
├── src/
│   └── worker.js          # Worker — serves /chat + handles /api/chat
├── public/
│   └── chat/
│       └── index.html     # Frontend (bundled into worker at deploy)
├── wrangler.toml
├── package.json
└── .gitignore
```
