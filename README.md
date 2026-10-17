# Canopy Clash — $CC

Single-file website + browser mini-game: `index.html`. No build step. Upload to GitHub Pages / Netlify / Vercel, or just open it.

## Setup
Open `index.html`, search for `var CONFIG` and fill in:

```js
tokenCA:  '',  // $CC mint → enables the "holder agent" balance check
buyUrl:   '',  // pump.fun page
chartUrl: '',  // chart link (auto-filled from the CA if blank)
xUrl:     'https://x.com/CanopyClashsol',
rpcUrl:   'https://api.mainnet-beta.solana.com', // swap for your own RPC (Helius, QuickNode…) if the public one rate-limits
minHold:  1,   // $CC needed to count as a holder
canDo / cantDo // the rules list shown on the site; keep them true
```

How it works:
- Connecting a wallet only reads the public address. The agent (class, colours, stats, name) is generated from that address.
- If `tokenCA` is set, the site reads the wallet's $CC balance via RPC and shows "HOLDER AGENT".
- Amber, vines, relic shards, XP and records are in-game only, saved in the visitor's browser (localStorage).
