# DivyaYatra — Temple Pilgrimage & Crowd Management Website

## 📁 Project Structure

```
divyayatra/
├── index.html              ← Homepage (hub — links to all features)
├── pilgrim-login.html      ← Pilgrim sign in / register (OTP + Email)
├── admin-login.html        ← Temple authority sign in (2FA secured)
├── admin-dashboard.html    ← Admin console (gated — admin session only)
├── crowd.html              ← Live Crowd Dashboard (deep page)
├── booking.html             ← Darshan Slot Booking (deep page)
├── temples.html             ← Temple Directory (deep page)
├── planner.html              ← Pilgrimage Route Planner (deep page)
├── darshan.html               ← Virtual Darshan (deep page)
├── reviews.html                ← Reviews & Community (deep page)
├── sos.html                      ← SOS & Lost and Found (deep page)
├── css/
│   ├── style.css             ← Core design system (colors, nav, cards, etc.)
│   └── pages.css             ← Shared patterns for standalone feature pages
├── js/
│   └── main.js               ← Shared interactive JavaScript
└── README.md
```

## 🔐 Access Control

- **Pilgrim pages** (`index.html`, `crowd.html`, `booking.html`, `temples.html`,
  `planner.html`, `darshan.html`, `reviews.html`, `sos.html`) all check for a
  `dy_pilgrim_session` in `sessionStorage` on load. No session → instant redirect
  to `pilgrim-login.html` (with a `?redirect=` back to the original page).
- **Admin dashboard** (`admin-dashboard.html`) checks for a separate
  `dy_admin_session` and redirects to `admin-login.html` if absent. Admin
  login requires Staff ID/email + password **and** a 2FA OTP step.
- Pilgrim and admin sessions are completely separate — logging into one
  does **not** grant access to the other.
- Sessions are stored in `sessionStorage`, so they clear when the browser tab closes
  (this is a front-end demo; wire up real authentication on a backend for production).

## 🚀 How to Open

1. Extract the ZIP folder
2. Double-click **index.html** — you'll be redirected to the pilgrim login first
3. Sign in with any mobile number / OTP (demo mode — any 6 digits work) to explore
4. For the admin console, go to `admin-login.html` and sign in there separately

## ✨ Site Map

| Page | Purpose |
|---|---|
| `index.html` | Homepage — hero, stats, links to all 7 feature pages |
| `crowd.html` | All-temple live crowd grid, gate breakdown, 7-day trend, FAQ |
| `booking.html` | Slot booking flow, temple availability table, policies, FAQ |
| `temples.html` | Full directory by region, search/filter, dress code guide |
| `planner.html` | Active itinerary + 6 curated multi-temple circuits |
| `darshan.html` | Live stream player, full stream grid, schedule, replays |
| `reviews.html` | Rating summary, review feed, top-rated temples, write-a-review |
| `sos.html` | Emergency SOS, lost & found board, safety tips, emergency contacts |
| `admin-dashboard.html` | Gate control, staff roster, live metrics (admin-only) |

## 🎨 Design System

- **Primary color:** Gold `#D4AF37`
- **Background:** Deep charcoal `#0a0602`
- **Typography:** Georgia (headings) + system sans-serif (body)
- **Background images:** Loaded from Unsplash (internet required for images)

## 📱 Responsive

Fully responsive — works on mobile, tablet, and desktop.

---
Made with devotion for every pilgrim. 🙏
