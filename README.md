# ⚡ HeyKay Stock Market Challenge

A real-time, two-player stock market competition page designed to be hosted for free on **GitHub Pages**. Players each pick a stock ticker and compete to see whose pick performs better each day.

---

## 🚀 Hosting on GitHub Pages (Quick Start)

1. **Create a new GitHub repository** (can be public or private with GitHub Pro)
2. **Upload all three files** to the root of the repo:
   - `index.html`
   - `admin.html`
   - `README.md`
3. Go to your repo **Settings → Pages**
4. Under *Source*, select **Deploy from a branch → main → / (root)**
5. Click **Save** — GitHub will give you a URL like `https://yourusername.github.io/repo-name/`
6. Open that URL — your challenge is live! 🎉

---

## ⚙️ First-Time Setup (Admin Panel)

1. Go to `https://your-github-pages-url/admin.html`
2. **Default password:** `heykay`
3. Set Player 1 name + ticker (e.g., HEYKAY → NVDA)
4. Set Player 2 name + ticker (e.g., JUSTIN → AAPL)
5. *(Optional but recommended)* Add your **Finnhub API key**
6. Click **SAVE SETTINGS**
7. Open `index.html` — data will start loading!

---

## 🔑 Getting a Free Finnhub API Key

The app works without an API key (uses Yahoo Finance via a public proxy), but a free Finnhub key gives you faster, more reliable real-time data:

1. Go to [finnhub.io](https://finnhub.io)
2. Sign up for a **free account** (no credit card needed)
3. Copy your API key from the dashboard
4. Paste it into the Admin Panel → Finnhub API Key field
5. Click **Test Key** to verify it works, then **Save Settings**

---

## 📺 Features

| Feature | Description |
|---|---|
| **Live Stock Prices** | Real-time prices via Finnhub or Yahoo Finance |
| **Two Player Cards** | Each player's ticker shown with price, % change, and direction arrow |
| **Winning Indicator** | Winning card glows gold with 👑 crown badge |
| **Leaderboard** | Running tally of who has won more days |
| **Market Countdown** | Live countdown to NYSE market close (4:00 PM ET) |
| **Market Indices** | DOW JONES, S&P 500, and NASDAQ in the footer bar |
| **Auto Refresh** | Data refreshes every 30 seconds automatically |
| **Admin Panel** | Password-protected settings page to change tickers, names, scores |

---

## 🔒 Admin Panel Features

- Change challenge title
- Set player names and ticker symbols
- Add/verify Finnhub API key
- Manually award wins (+1 to either player)
- Reset scores to zero
- Change admin password (uses SHA-256 hashing)

**Default admin password:** `heykay`
*(Change this immediately in the Admin Panel → Change Password section)*

---

## 📊 Stock Data Sources

The app tries data sources in this order:

1. **Finnhub API** (if key provided) — Real-time, CORS-friendly, reliable
2. **Yahoo Finance via corsproxy.io** — Free fallback, no key needed
3. **Yahoo Finance via api.allorigins.win** — Secondary fallback

Market indices (DOW, S&P 500, NASDAQ) always use Yahoo Finance via CORS proxy.

---

## 🎮 How the Challenge Works

- Each player picks a stock ticker (set via Admin Panel)
- The player whose stock has a **higher % daily gain** is currently winning
- The **winning card glows gold** with a crown icon
- At **4:00 PM ET** each trading day, a win is automatically recorded to the leaderboard
- Check the **Leaderboard** panel (top right) to see the all-time score

---

## 🛠️ File Structure

```
stock-challenge/
├── index.html   ← Main challenge display (put this URL on a TV!)
├── admin.html   ← Password-protected settings page
└── README.md    ← This file
```

All settings are stored in browser **localStorage** — no server or database needed.

---

## 💡 Tips

- **Display on a TV or second monitor** for the full effect — the design is built for that!
- Use a ticker like `^DJI` for the DOW directly in a player card (works as a player ticker too)
- The countdown automatically handles EST/EDT daylight saving time
- Weekends show "MARKET CLOSED — WEEKEND" instead of a countdown
- After market hours the cards show "CLOSED" or "AFTER HRS" status

---

## 🔗 Valid Ticker Examples

| What you want | Ticker to use |
|---|---|
| Apple | AAPL |
| NVIDIA | NVDA |
| Tesla | TSLA |
| Microsoft | MSFT |
| S&P 500 ETF | SPY |
| Bitcoin (if on Finnhub plan) | BINANCE:BTCUSDT |
| DOW Jones Index | ^DJI |

---

*Built with vanilla HTML/CSS/JavaScript — no frameworks, no build step, no server required.*
