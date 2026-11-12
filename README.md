# Sync — community platform for builders

Build logs, questions, launches and co-founder posts, organised into Spaces, with upvotes, comments, profiles and an automatic quality filter.
Zero dependencies — only Node.js 18+. Data is stored in `data/db.json`.

## Run locally
    node server.js        # http://localhost:3000

## Deploy
- **Any VPS:** install Node 18+, upload the folder, run `NODE_ENV=production PORT=3000 node server.js` under pm2/systemd, put Nginx/Caddy in front for HTTPS.
- **Docker:** `docker build -t sync . && docker run -p 3000:3000 -v sync-data:/data sync`
- **Render / Railway / Fly.io:** create a Node web service, start command `node server.js`, and attach a persistent disk mounted at the `DATA_DIR` you set (e.g. `/data`).

Env vars: `PORT`, `NODE_ENV=production` (secure cookies — requires HTTPS), `DATA_DIR`.
Back up by copying `data/db.json`. For heavy traffic, swap the JSON store for Postgres.
