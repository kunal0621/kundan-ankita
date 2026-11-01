# Digital Wedding Invitation (Shaadi Card)

A luxury, interactive digital Indian wedding card web application inspired by traditional royal aesthetics and Gond folk art.

This repository is customized for **Kundan & Ankita** with the **Groom details positioned first**, and upgraded with a **dynamic configuration system** (`config.json` & `config.js`) supporting multi-day celebrations:
- **30 Nov**: Tilak Ceremony (The Riwaaz - Banquet, Katras)
- **05 Dec**: Haldi Ceremony (Thakur Badi, Baghmara)
- **06 Dec**: Mehandi & Sangeet Night (Thakur Badi, Baghmara)
- **07 Dec**: Barat & Shubh Vivah (BHAGWAN PALACE, Deoghar)

---

## ✨ Features

- **🤵 Groom Details First**: Kundan Singh & Ankita Singh. Groom's name and illustrated portrait are positioned first throughout the entire invitation (Hero, Portraits, Royal Seal, Loader, Blessings, Calendar, and Share Dialog).
- **📅 4-Function Itinerary Timeline**:
  - **Day 1 (Mon, 30 Nov)**: Tilak Ceremony
  - **Day 2 (Sat, 05 Dec)**: Haldi Ceremony
  - **Day 3 (Sun, 06 Dec)**: Mehandi & Sangeet Night
  - **Day 4 (Mon, 07 Dec)**: Barat & Shubh Vivah
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
    "description": "You are invited to the wedding celebrations of Kundan Singh & Ankita Singh · 30 November – 7 December 2026"
  },
  "couple": {
    "groom": {
      "name": "Kundan Singh",
      "heroName": "Kundan",
      "hindi": "कुंदन सिंह",
      "role": "The Groom",
      "portrait": ""
    },
    "bride": {
      "name": "Ankita Singh",
      "heroName": "Ankita",
      "hindi": "अंकिता सिंह",
      "role": "The Bride",
      "portrait": ""
    },
    "monogram": "K & A"
  },
  "wedding": {
    "topBlessing": "॥ जय गणेशाय नमः ॥",
    "subBlessing": "॥ शुभ विवाह ॥",
    "sealMantra": "SHUBH VIVAH ✦ KUNDAN & ANKITA ✦ 30 NOV – 7 DEC 2026 ✦",
    "sealTap": "Tap to open",
    "gateInviteHi": "आप सादर आमंत्रित हैं",
    "gateInviteEn": "You are cordially invited",
    "gateDate": "30 November – 7 December 2026",
    "eyebrow": "Together with their families",
    "invitationLine": "request the honour of your presence as they begin their forever",
    "dates": {
      "ariaLabel": "Monday 30 November to Monday 7 December 2026",
      "startDay": "Mon",
      "startDate": "30",
      "endDay": "Mon",
      "endDate": "07",
      "monthYear": "Nov – Dec 2026"
    }
  },
  "countdown": {
    "target": "2026-11-30T17:00:00+05:30",
    "note": "until the tilak begins · Monday, 30 November"
  },
  "venue": {
    "name": "Wedding Celebrations · Jharkhand",
    "address": "30 Nov (Tilak): The Riwaaz - Banquet, Katras (828114)\n5 & 6 Dec (Haldi & Mehandi): Thakur Badi, Baghmara (828306)\n7 Dec (Barat): BHAGWAN PALACE, Deoghar (814112)"
  },
  "days": [
    // Day 1: Tilak (30 Nov) - The Riwaaz, Katras
    // Day 2: Haldi (05 Dec) - Thakur Badi, Baghmara
    // Day 3: Mehandi & Sangeet (06 Dec) - Thakur Badi, Baghmara
    // Day 4: Barat & Shubh Vivah (07 Dec) - BHAGWAN PALACE, Deoghar
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
