# Dynamic Dashboard 🦈  
A Modern Finance Dashboard builder

Dynamic Dashboard is a full-featured finance dashboard builder built with **Next.js (App Router)**, **Redux Toolkit**, and **modern charting libraries**.  
It supports **real-time market data**, **watchlists**, **widgets**, **advanced search**, and **interactive charts (line & candlestick)** using real APIs no hard-coded data.

---

https://github.com/user-attachments/assets/d015b915-8c26-4eef-ba18-a9384c441e06


https://github.com/user-attachments/assets/f2b9ea9f-bcf5-4291-85ed-004e2a6968b4

<img width="1916" height="971" alt="Screenshot 2025-12-25 231346" src="https://github.com/user-attachments/assets/673030b1-cbe0-4554-a108-847e70a51b16" />

<img width="1916" height="1027" alt="Screenshot 2025-12-25 231429" src="https://github.com/user-attachments/assets/c09daec6-5f21-45df-8a5b-1177816f77cc" />

<img width="1920" height="1080" alt="Screenshot 2025-12-26 162711" src="https://github.com/user-attachments/assets/0de9e276-9158-4db9-9930-ccd0036ea5c2" />

<img width="1920" height="1020" alt="Screenshot 2025-12-26 171227" src="https://github.com/user-attachments/assets/f8e07802-e5e3-42e9-8ae2-b05aac6dcc1b" />

<img width="1919" height="967" alt="Screenshot 2025-12-28 180048" src="https://github.com/user-attachments/assets/7cb7b469-e343-4a88-878f-41a2e2d085c0" />


<img width="1919" height="966" alt="Screenshot 2025-12-28 185540" src="https://github.com/user-attachments/assets/4c8a42bf-a131-4458-8470-42ef6895e38f" />

<img width="1920" height="1020" alt="Screenshot 2025-12-27 233746" src="https://github.com/user-attachments/assets/a7fc6062-9514-4678-b63f-70f5fbbc313c" />

<img width="1920" height="1020" alt="Screenshot 2025-12-27 233819" src="https://github.com/user-attachments/assets/dffbf203-993c-49b9-ab0f-168d0b47f6f8" />

<img width="1917" height="966" alt="Screenshot 2026-01-09 030415" src="https://github.com/user-attachments/assets/d2a5d54b-2989-4caa-97eb-6186fd7a05fb" />


<img width="1920" height="1080" alt="Screenshot 2025-12-27 021710" src="https://github.com/user-attachments/assets/3246953e-e174-42cf-bacf-c1c8716dcef5" />

<img width="1920" height="1020" alt="Screenshot 2025-12-27 233731" src="https://github.com/user-attachments/assets/0614eec2-7911-4a6c-960e-1f0879a61042" />


<img width="1920" height="1020" alt="Screenshot 2025-12-27 190752" src="https://github.com/user-attachments/assets/78e62b37-a180-47af-8eb0-f35c2b1b2b6a" />

---

## 🚀 Features Overview

### 🔹 Market Coverage
* Indices  → Alpha Vantage API
* Crypto → CoinRanking API (RapidAPI)
* Stocks  → Alpha Vantage API
* Futures  → Alpha Vantage API
* Forex  → Alpha Vantage API
* F&O  → Alpha Vantage API

### 🔹 Live Market Data
* **Stocks / Indices / Forex** → Alpha Vantage API
* **Crypto** → CoinRanking API (RapidAPI)
* No hard-coded prices — all data is fetched live

### 🔹 UI & UX
* Color-coded price changes (Green ↑ / Red ↓)
* Expandable market categories with smooth animations
* Loading states while fetching data
* Responsive layout with dark theme

---

## 📁 Project Structure

```
Dynamic_Dashboard/
│
├── public/
│
├── src/
│
│   ├── app/
│   │   ├── layout.js                    # App shell + BottomNav
│   │   ├── providers.js                 # Redux provider
│   │   ├── globals.css                  # Soft dark theme only
│   │   ├── page.js                      # Default → widgets
│   │
│   │   ├── watchlist/
│   │   │   ├── page.js                  # Market watch table
│   │   │   ├── ViewWatchlistModal.js
│   │   │   └── CreateWatchlistModal.js
│   │
│   │   ├── chart/                       #  FULL SCREEN CHART
│   │   │   ├── page.js                  # Chart page (symbol-based)
│   │   │   ├── ChartHeader.js           # Name, price, interval selector
│   │
│   │   ├── widgets/
│   │   │   ├── page.js                  # Widget grid (default page)
│   │   │   └── AddWidgetModal.js
│   │
│   │   ├── explore/
│   │   │   └── page.js
│   │
│   │   ├── community/
│   │   │   └── page.js
│   │
│   │   ├── menu/
│   │   │   └── page.js
│   │
│   │   └── api/
│   │       └── proxy/
│   │           ├── route.js              # Snapshot + router
│   │           └── history/
│   │               ├── alpha
│   │                   └── route.js
│
│   ├── components/
│   │   ├── BottomNav.js
│   │   ├── WidgetCard.js                 # card / table / chart
│   │   ├── JsonExplorer.js 
│   │   ├── DashboardBackup.js 
│
│   ├── charts/                           #  CHART ENGINE
│   │   ├── ChartRenderer.js              # Chart.js wrapper
│   │   ├── CandleChart.js
│   │
│
│   ├── store/
│   │   ├── index.js                      # configureStore
│   │   ├── watchlistSlice.js
│   │   ├── marketDataSlice.js            # snapshot only
│   │   └── widgetsSlice.js
│
│   ├── lib/
│   │   ├── fetchers/
│   │   │   ├── snapshotFetcher.js        # watchlist/widgets prices
│   │   │   ├── historyFetcher.js         # charts history only
│   │   │   ├── widgetFetcher.js
│   │   │   └── cache.js                  # shared cache helper
│   │   │
│   │   ├── normalizers/
│   │   │   ├── stockHistory.js           # Alpha → chart data
│   │   │   ├── cryptoHistory.js          # CoinRanking → chart data
│   │   │   └── cryptoNormalizer.js       # CoinRanking → snapshot
│   │   │
│
├── .env.local
├── package.json
└── README.md

```


---

## 📊 Market Data Architecture

### Snapshot Data (Prices, % Change)
* Fetched via `/api/proxy`
* Uses **Alpha Vantage GLOBAL_QUOTE**
* Cached for 5 minutes at the **server level**
* Stored in Redux (`marketDataSlice`) for UI rendering

### Historical Data (Candlestick Charts)
* Fetched via `/api/proxy/history/alpha`
* Uses **Alpha Vantage TIME_SERIES_DAILY**
* Loaded **only when switching to candlestick view**

---

## 📈 Chart System

### Line Chart
* Uses cached snapshot data
* No additional API calls
* Rendered via `ChartRenderer.js` (Chart.js wrapper)

### Candlestick Chart
* Uses **Lightweight Charts v5**
* Fetches OHLC data only when needed
* Fully interactive (zoom, pan, crosshair)

---

## ⭐ Watchlist Dashboard

### Supported Features
* Multiple watchlists
* Active watchlist switching
* Add / remove instruments
* Delete watchlists
* UI flags for modals

### Watchlist Creating Modal
* Opens when isCreatingWatchlist === true
* Contains: Input (watchlist name)
* Create / Cancel buttons
* Watchlist buttons
* Rendered from state.watchlist.watchlists
* Clicking → setActiveWatchlist(id)

### User actions
* User clicks + Create Watchlist, a modal opens
* User types watchlist name, clicks Create, closes the modal
* In that Modal user also has the option to set Active that watchlist
* New watchlist appears as a tab button
* That watchlist becomes active
* Now in the dashboard user can click on any watchlist and set Active that watchlist so any instruments he stars goes to that active watchlist
* User has another option to view the watchlist, he clicks on the eye icon and ViewWatchlistModal opens and in that modal the list appears and from this modal he can remove any instrument and can also delete the whole watchlist

* All powered by **Redux Toolkit (`watchlistSlice`)**.

---

## 🧩 Widgets Dashboard

### widgets/page.js
* Main widgets dashboard
* Displays added widgets
* Shows "+ Add Widget" placeholder
* Controls AddWidgetModal visibility

### AddWidgetModal.js
* Create custom widgets
* Configure:
  * Widget name
  * API source
  * Refresh interval
  * View type (card / table / chart)

---

## 🔍 Search System (No Extra APIs)

### How Search Works
* Source of truth: `marketDataSlice.categories`
* Filters instruments by name or symbol
* Uses **Fuse.js** for fuzzy search

### Examples
* Handles Spelling errors done by the User while search
"Telsa" → Tesla Inc (TSLA)
"Aplei" → Apple Inc (AAPL)


### On Selection
* Sets active instrument
* Loads chart using cached snapshot or history

---

## 🧠 Caching Strategy

### Cache #1 — Server Cache (API Proxy)
* Lives inside `/api/proxy`
* Prevents repeated Alpha Vantage calls
* TTL = 5 minutes

### Cache #2 — Client Cache (Redux)
* Stores snapshot prices
* Used for UI rendering
* Does NOT prevent API calls

---

## 🔄 Data Flow (Clear Mental Model)
```
Search / Watchlist
↓
GLOBAL_QUOTE (Alpha Vantage)
↓
API Proxy Cache
↓
Redux Snapshot
↓
Line Chart (No API)
```
* For Line Chart /api/proxy?function=GLOBAL_QUOTE&symbol=NVDA

```
Candlestick Chart
↓
TIME_SERIES_DAILY
↓
/api/proxy/history/alpha
↓
Lightweight Charts
```
* For Candle Stick Graph /api/proxy/history/alpha?symbol=AAPL&interval=1D


✅ hits Alpha Vantage  
❌ But subsequent calls may be served from **server cache**

Browser always calls `/api/proxy`  
Proxy only calls Alpha Vantage when cache expires

---

## 🧠 Why This Architecture Works

* Prevents API rate-limit issues
* Zero redundant network calls
* Scales well for large watchlists
* Clear separation of concerns
* Production-grade data flow

---

## 🏁 Conclusion

Dynamic Dashboard is a **production-ready finance dashboard** demonstrating:
* Real API integration
* Advanced state management
* Clean architecture
* Scalable frontend design
* Professional charting solutions

---

## 🔮 Future Scope & Enhancements

The current implementation lays a strong foundation, and the platform can be extended further with the following enhancements:

* 🧲 **Drag & Drop Widgets**
  * Allow users to freely rearrange widgets on the dashboard using drag-and-drop.
  * Save widget layout preferences per user.
  * Improves personalization and dashboard flexibility.

* 🏷️ **Company Logos & Branding**
  * Display official company logos alongside stock names and symbols.
  * Fetch logos dynamically using symbol-based logo APIs.
  * Enhances visual clarity and brand recognition.

* ⏱️ **Real-Time Streaming Updates**
  * Integrate WebSockets or Server-Sent Events (SSE) for live price updates.
  * Reduce polling-based API calls.
  * Enables near real-time market movement tracking.

* 📐 **Resizable Widgets**
  * Allow users to resize widgets (small / medium / large).
  * Better support for different data views like tables vs charts.


* 📱 **Mobile-First Enhancements**
  * Optimize chart interactions for touch gestures.
  * Improve widget layout responsiveness on smaller screens.


---


## 🙌 Author
Built with ❤️ by **Alisha Mahmood**

