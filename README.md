# Digital Wedding Invitation (Shaadi Card)

A luxury, interactive digital Indian wedding card web application inspired by traditional royal aesthetics and Gond folk art.

This repository is customized for **Kundan & Ankita** with the **Groom details positioned first**, and upgraded with a **dynamic configuration system** (`config.json` & `config.js`) supporting multi-day celebrations:
- **Day 1 (01 Dec)**: Haldi Ceremony
- **Day 2 (02 Dec)**: Mehandi & Sangeet Night
- **Day 3 (03 Dec)**: Shaadi & Phere (Wedding Ceremony)
- **Day 5 (05 Dec)**: Grand Wedding Reception

---

## ✨ Features

- **🤵 Groom Details First**: Kundan & Ankita. Groom's name and illustrated portrait are positioned first throughout the entire invitation (Hero, Portraits, Royal Seal, Loader, Blessings, Calendar, and Share Dialog).
- **📅 4-Function Itinerary Timeline**:
  - **Day 1 (Tue, 01 Dec)**: Haldi Ceremony (Morning & Afternoon)
  - **Day 2 (Wed, 02 Dec)**: Mehandi & Sangeet Night (Evening)
  - **Day 3 (Thu, 03 Dec)**: Shaadi & Phere (Auspicious Wedding Muhurat)
  - **Day 5 (Sat, 05 Dec)**: Grand Wedding Reception (Royal Evening Banquet)
  - Interactive multi-tab switcher with spring physics pill animation
  - Bilingual English and Hindi descriptions
  - Color-coded ceremony badges with custom vector SVG icons (including dedicated henna mandala for Mehandi)
- **📂 Dynamic Configuration (`config.json` & `config.js`)**: All names, dates, events, venues, descriptions, and greetings are decoupled from HTML.
- **🌐 100% Offline & Online Compatibility**: Works seamlessly both when double-clicked directly from your file system (`file:///`) and when served over HTTP/HTTPS (Vercel, local server).
- **🚪 Royal Gate Opening Ceremony**: Interactive royal palace doors with gold latches that part open on tap/click with smooth entrance choreography.
- **🎨 Gond Art & Traditional Motifs**: 100% procedural vector SVG artwork (Tree of Life, Peacocks, Rosettes, Toran, Kalash).
- **🌸 Ambient Falling Petals**: Floating golden marigold petals drifting down the invitation.
- **🎶 Ambient Background Wedding Music**: Seamlessly plays the wedding soundtrack in the background as guests enter the invitation, with zero clutter or on-screen widgets.
- **⏳ Live Countdown Timer**: Animated Gond sun-dial counting down days, hours, minutes, and seconds in real-time.
- **🗓️ 1-Click "Add to Calendar"**: Generates a standard `.ics` iCalendar file for all wedding events.
- **📍 Venue & Navigation**: Embedded venue card with one-tap Google Maps directions.
- **💌 Shareable**: Integrated with the Web Share API and a copy-to-clipboard fallback with toast notifications.
- **⚡ Zero Build Dependencies**: Pure HTML5, CSS3, and Vanilla JavaScript with Framer Motion (`motion.js`) loaded via CDN. No compilation or node_modules required.

---

## 🚀 Quick Start (Run & Preview)

### Option 1: Direct File Open (Offline)
Simply double-click [`index.html`](index.html) to open in your favorite web browser. Thanks to the `<script src="config.js">` bridge, all your customized details will load without local file CORS blocking.

### Option 2: Using Python's Local Server
Run in your terminal from this folder:

```bash
python -m http.server 3000
```

Then open [http://localhost:3000](http://localhost:3000) in your browser.

---

## 🛠️ Customizing Details

You can edit your wedding details in either [`config.json`](config.json) (for web hosting / Vercel) or [`config.js`](config.js) (for local offline opening). Both files stay in sync.

```json
{
  "meta": {
    "title": "Kundan & Ankita · Shubh Vivah",
    "description": "You are invited to the wedding celebrations of Kundan & Ankita · 1–5 December 2026"
  },
  "couple": {
    "groom": {
      "name": "Kundan",
      "heroName": "Kundan",
      "hindi": "कुंदन",
      "role": "The Groom",
      "portrait": ""
    },
    "bride": {
      "name": "Ankita",
      "heroName": "Ankita",
      "hindi": "अंकिता",
      "role": "The Bride",
      "portrait": ""
    },
    "monogram": "K & A"
  },
  "wedding": {
    "topBlessing": "॥ जय गणेशाय नमः ॥",
    "subBlessing": "॥ शुभ विवाह ॥",
    "sealMantra": "SHUBH VIVAH ✦ KUNDAN & ANKITA ✦ 1 – 5 DECEMBER 2026 ✦",
    "sealTap": "Tap to open",
    "gateInviteHi": "आप सादर आमंत्रित हैं",
    "gateInviteEn": "You are cordially invited",
    "gateDate": "1 – 5 December 2026",
    "eyebrow": "Together with their families",
    "invitationLine": "request the honour of your presence as they begin their forever",
    "dates": {
      "ariaLabel": "Tuesday 1 to Saturday 5 December 2026",
      "startDay": "Tue",
      "startDate": "01",
      "endDay": "Sat",
      "endDate": "05",
      "monthYear": "December 2026"
    }
  },
  "countdown": {
    "target": "2026-12-01T11:00:00+05:30",
    "note": "until the haldi begins · Tuesday, 1 December"
  },
  "venue": {
    "name": "Krishnam Resort & Marriage Garden",
    "address": "Damoh, Madhya Pradesh",
    "mapUrl": "https://maps.app.goo.gl/imVwWHP4Yv332h2F8"
  },
  "days": [
    // Day 1: Haldi (01 Dec)
    // Day 2: Mehandi (02 Dec)
    // Day 3: Shaadi (03 Dec)
    // Day 5: Reception (05 Dec)
  ]
}
```

---

## 🌐 Deploying to GitHub Pages (Free Web Hosting)

This repository includes an automated GitHub Actions deployment workflow ([`.github/workflows/deploy.yml`](.github/workflows/deploy.yml)).

### Steps to activate GitHub Pages:

1. **Push your code to GitHub**:
   ```bash
   git push origin main
   ```
2. In your repository on GitHub, go to **Settings** > **Pages** (in the left sidebar).
3. Under **Build and deployment** > **Source**, select **GitHub Actions**.
4. Run the workflow manually from the **Actions** tab by selecting **Deploy to GitHub Pages** and clicking **Run workflow**. Once completed, your site will be published at:
   ```
   https://<your-username>.github.io/<repository-name>/
   ```
   For example: `https://<your-username>.github.io/kundan-ankita/`

The deployment workflow is configured with `workflow_dispatch`, allowing manual on-demand deployments whenever you are ready.

---

## 🚢 Alternative: Deploying to Vercel

1. Push your changes to GitHub:
   ```bash
   git add .
   git commit -m "Update wedding invitation"
   git push origin main
   ```
2. Log in to [Vercel](https://vercel.com/) and click **Add New > Project**.
3. Import your repository.
4. Leave all settings at default (**Other** preset, no build command).
5. Click **Deploy**. Your wedding card will be live instantly!
