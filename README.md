# Split Ledger — UPI Split QR Generator

A single static page. Enter a UPI ID, account holder name, and a total amount —
it splits the amount into chunks of ₹1,999 or less and generates one scannable
UPI QR code per chunk. Everything runs client-side; nothing is sent to a server.

## Deploy to Vercel

**Option A — Vercel CLI (fastest)**
```bash
npm i -g vercel     # if you don't have it already
cd upi-split-qr
vercel               # follow the prompts, accept defaults
vercel --prod        # promote to your production URL
```

**Option B — GitHub + Vercel dashboard**
1. Push this folder to a new GitHub repo.
2. Go to https://vercel.com/new, import the repo.
3. Framework preset: "Other" (or leave as detected) — no build command needed,
   output directory is the repo root. Click Deploy.

**Option C — Drag and drop**
Go to https://vercel.com/new, and drag the `upi-split-qr` folder onto the page.

No environment variables, database, or backend are required.

## Customizing
- `MAX_PER_QR` in the `<script>` block controls the per-QR cap (default 1999).
- Colors and type are defined as CSS custom properties near the top of the
  `<style>` block in `index.html`.
