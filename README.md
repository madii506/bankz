# bankz

The bank of the city. A terminal on Solana with a vault inside: lock any token in a safe-deposit box that nobody can open before its date (a Jupiter Lock escrow with cancel and redirect switched off), watch every box on the vault wall, earn a card tier, cash memes out at the teller and move SOL into tokenized gold or the S&P 500. Around it: tokenized stocks, Jupiter perps, the pump.fun trenches and the city.

- `/` home: one screen. Two steel vault doors are shut when you arrive: hold anywhere (or any key) and the wheel spins up, four brass bars pull back across the seam and the doors slide apart onto the emerald city; leave it alone and they open by themselves in about two seconds. Live boxes rise out of the city as deposit slips. All of it is CSS and inline SVG, no images.
- `/app` the terminal. Key 0 opens the vault: lock a bag, the wall, your card, teller, savings. Arriving from the home, the same doors part again.
- Receipts: every lock, claim and trade that Solana confirms prints a receipt (account number, barcode from the signature, Solscan link). Save it as a picture or post it; left alone it files itself into the statement (the receipt icon in the bar, or type `statement`). The statement lives in this browser only.
- Every lock and claim is dry-run on the server (`sim`, simulateTransaction) before the wallet is asked to sign.
- `api/m.js` one Vercel function: prices, quotes, swaps, perps, trenches, the city, the box registry (`boxes`, `boxadd`) and the dry run (`sim`). Locks are built and signed in the browser; the registry only lists boxes the chain confirms.

Launch settings: `assets/js/config.js` (`window.BANKZ = { ca, x }`). Postgres via `DATABASE_URL` (tables `bz_boxes`, `bz_city`, `mk_img`).
