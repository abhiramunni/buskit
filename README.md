# BusKit — Bengaluru Bus, Sorted

Never miss the bus. Never overpay for it. BusKit is a single-file web app for
Bengaluru bus riders: next departures from your stop, a route finder with
honest fares, and the pass maths that tells you whether a monthly pass actually
saves you money.

**Live:** https://abhiramunni.github.io/buskit/

## What it does

- **The departure board** — a split-flap style live board showing the next bus
  from your stop, with the fare to the end of the route. Pick any of the 27
  stops as your home stop. Tap a row for every stop on that route, first/last
  bus and frequency.
- **Find a route** — pick From and To. BusKit checks 12 BMTC routes and shows
  the quickest ways there: direct first, then the best one-change options with
  the change stop, fare, distance and time. A note tells you when a ₹70 day
  pass covers the return trip.
- **Fares & passes** — November 2026 BMTC slabs (minimum ₹10, maximum ₹45 on
  ordinary buses) with a distance slider for Ordinary, Vajra AC and Airport
  (Vayu Vajra) services. A second calculator compares single tickets, day
  passes and the ₹1,050 monthly pass for your actual riding habit.
- **Your routes** — save the routes you ride every day; one tap opens them.
- **My trips this week** — log each ride and see the week's spend against the
  monthly-pass pace.
- **Bus news, this week** — the three rider-relevant stories: 200 new
  mini-buses for Metro feeders, the fare hike (min ₹10, max ₹45), and the
  seats-only rule under the Shakti scheme — plus a plain-words Shakti explainer
  (free for women with a Karnataka domicile on ordinary buses).
- **Guides, in plain words** — six short explainers: reading the route board,
  Shakti step by step, day pass vs monthly pass, paying without cash, rush
  hour, and what to do if the bus doesn't come.

## The numbers in the app

- 12 routes (500D, 505, 201E, 315P, 15E, 365J, V-365J, 600, 210A, 504, 401K,
  KIAS-8) across 27 stops on Bengaluru's main corridors. Route numbers,
  stop order and distances are representative of the published network;
  timings are the published first/last bus and frequency for each route.
- Fares follow the BMTC stage slabs in force from 5 November 2026
  (₹10 / ₹15 / ₹20 / ₹25 / ₹30 / ₹35 / ₹40 / ₹45 by distance; Vajra AC is
  roughly double, capped at ₹90; airport buses are a flat ₹250). Pass prices
  (day ₹70, monthly ₹1,050) are indicative November 2026 figures.
- Everything is labelled indicative in the app: the board at the stop and the
  BMTC app are the final word before you travel.

## How it works

- One self-contained `index.html` — no backend, no signup, no tracking.
- All data lives in your browser (localStorage): home stop, saved routes,
  trip log, coach state. "Remove sample trips" clears the seeded week;
  "Erase everything" (two taps) resets the app.
- Cinematic intro animation (tap to skip; quick version on return visits),
  3-step onboarding coach, warm editorial design (ivory paper, espresso ink,
  bronze and terracotta), Fraunces + Inter, Ken Burns photography.
- Works offline once loaded — timetables and fares are computed on-device
  from the published schedule, not fetched live.

## Files

- `index.html` — the app (this repo serves it via GitHub Pages)
- `buskit-hero.webp`, `buskit-flatlay.webp` — photography used by the app
- `README.md` — this file
- `LICENSE` — MIT

## Build & test

Built from 10 source chunks and assembled locally; QA is a headless jsdom
suite (`qa-test.js`, 114 assertions: fare table, next-departure maths, route
finder cases, pass maths, trip log, saved routes, guides, sheets, intro).
Run with `node qa-test.js` — it must print `114 passed, 0 failed`.

## License

MIT — see `LICENSE`.
