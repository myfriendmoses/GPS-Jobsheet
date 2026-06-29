# GPS - Jobsheet Generator Application

A mobile-optimized, single-file Progressive Web Application (PWA) built for **Goodwin Piloting Services** to dynamically generate alignment-padded, monospaced jobsheets for transit operations. This tool runs entirely in the browser, offers automatic field state preservation, and relies on strict structural padding for easy copy-paste reporting.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![PWA](https://img.shields.io/badge/PWA-5A0FC8?style=flat-square&logo=progressive-web-apps&logoColor=white)

---

## 🚀 Key Features

* **PWA Gate Shield:** A premium fullscreen security layer that prevents standard mobile browser access until users add the application to their home screen. Includes contextual onboarding guides for both **iOS Safari** and **Android Chrome**.
* **Smart Address Autocomplete:** Powered by the native `AddySolutions` (Addy.co.nz) engine to autocomplete highly accurate New Zealand street addresses for both Start and End route nodes.
* **15-Minute Time Rounding Machine:** Standardizes input logistics by automatically rounding blurred time parameters (`timeReq`, `timeBase`, `startTime`, etc.) to the nearest 15-minute interval.
* **Persistent Local Storage:** Instantly mirrors user form actions to `localStorage`. Includes a UI visual confirmation tracker (`Autosaved ✓`) to ensure pilot data is never lost mid-transit.
* **Monospaced Summary Formatting:** Maps form fields to a strict character-padded plain-text layout using monospaced spacing rules (`"Courier New"`). Handles automatic word-wrapping constraints safely on longer text areas like Notes.

---

## 🛠️ Tech Stack & Architecture

The tool is completely engineered within a highly portable, modern **Single-File App (SFA)** model:

* **Markup & UI:** Semantic HTML5 structuring using responsive CSS Flexbox/Grid tokens, mimicking heavy frameworks but maintaining sub-millisecond execution speeds.
* **Data Layer:** Native JavaScript state bindings synchronized on target `input` listener triggers.
* **API Integration:** Integrated async address lookups using `https://www.addysolutions.com`.
* **Caching & Worker States:** Embedded inline JavaScript Blob Service Worker setup allows the layout shell to perform offline fetches gracefully.

---

## 📋 Tracking & Mathematical Metrics

The application captures critical operational compliance and logistical dimensions:

### Form Parametrics
* **Core Identifiers:** Auto-generated Unique IDs (`GPS-XXXXXX`), Customer Name, Order/PO Numbers.
* **Permits:** OPIA Permit and Rail Permit code entries.
* **Logistics Matrix:** Dual mileage records mapping **Base Mileage**, **Start Mileage**, **End Mileage**, and final **Base Mileage (E)** with corresponding timestamps.

### Dynamic Calculus Fields
The application automatically resolves runtime statistics on every input change:
* **Base to Start:** `Start KM` minus `Base KM`
* **Pilot Mileage:** `End KM` minus `Start KM`
* **End to Base:** `Base KM (E)` minus `End KM`
* **Pilot Time:** Time spent piloting, subtracting standby durations (rendered in decimal hours).
* **Timesheet Total:** Overall operational window from base departure to base arrival.

---

## 📦 Distribution & Deployment

Because the stack relies completely on client-side compilation, deployment requires zero cloud infrastructure pipeline dependencies.

### Static Cloud Hosting (Recommended)
You can directly link the repository root to static rendering containers such as **GitHub Pages**, **Vercel**, **Netlify**, or **Cloudflare Pages**. Ensure your corporate pilot branding icon (`logo.png`) rests in the same operational route path.

### Local Development Workspace Run
```bash
# Spin up via python standard routing 
python -m http.server 8080

# Or via Node workspace serve
npx serve .
