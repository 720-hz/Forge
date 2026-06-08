# 🔥 Forge — Calorie Tracker & AI Coach

A complete, production-ready fitness app built with **Capacitor** (web tech wrapped in a real native Android shell). This guide takes you from zero to a published app on Google Play.

> **You do not need to be a developer to follow this.** Every command is spelled out. Budget about 2–3 hours for your first build, most of which is installing tools and waiting for downloads.

---

## What's inside

```
forge-coach-app/
├── www/                    ← the entire app (this is what runs)
│   ├── index.html
│   ├── styles.css
│   └── app.js
├── resources/              ← app icon + splash screen sources
│   ├── icon.png            (1024×1024 — used to generate all icon sizes)
│   ├── splash.png          (2732×2732 — used for the launch screen)
│   ├── icon-source.svg
│   └── splash-source.svg
├── capacitor.config.json   ← app name, ID, splash/status bar config
├── package.json            ← dependencies
└── README.md               ← you are here
```

## Features

- **Smart onboarding** → calculates your real targets (BMR via Mifflin-St Jeor, TDEE, deficit/surplus, macros)
- **Daily dashboard** → calorie ring, macros, water, steps, today's workout, meal suggestions
- **Food logging** → 60+ food library, custom foods, favorites, recents, saveable custom meals
- **Live workout logger** → log sets/reps/weight in real time with an auto rest timer; pre-fills last session's weights
- **Cardio logging** → calorie burn estimated from MET values and body weight
- **Body tracking** → weight chart, body measurements, Navy-method body-fat estimate, progress photos (camera)
- **Personal records** → auto-detected from your logged sets, with estimated 1-rep max
- **Exercise library** → 35+ exercises with form cues
- **History** → calendar of every logged day, tap to review
- **Weekly review** → auto-generated insights and adherence score
- **Achievements** → 24 milestones to unlock
- **Reminders** → meal, water, workout, and weigh-in notifications
- **Coach** → personalized nutrition, training, and lifestyle protocols
- **Data export** → full JSON backup
- **100% offline & private** → all data stays on the device; no servers, no accounts, no ads

---

## PART 1 — Install the tools (one time)

You need three things installed on your computer.

### 1. Node.js (version 18 or newer)
Download the **LTS** version from <https://nodejs.org> and install it.
Verify in a terminal:
```bash
node --version    # should print v18.x or higher
npm --version
```

### 2. Java JDK 17
Android builds need Java 17. Download from <https://adoptium.net> (Temurin 17).
Verify:
```bash
java -version     # should print version 17.x
```

### 3. Android Studio
Download from <https://developer.android.com/studio> and install with default options.
On first launch it will download the **Android SDK** — let it finish. Then:
- Open **Settings → Languages & Frameworks → Android SDK**
- On the **SDK Platforms** tab, check **Android 14 (API 34)**
- On the **SDK Tools** tab, make sure **Android SDK Build-Tools** and **Android SDK Platform-Tools** are checked
- Click **Apply** to download them.

---

## PART 2 — Build the app

Open a terminal **inside the `forge-coach-app` folder** and run these in order.

### 1. Install dependencies
```bash
npm install
```

### 2. Initialize Capacitor (only if it asks — config is already provided)
The project already has `capacitor.config.json`, so you can skip `cap init`. If for any reason it complains, run:
```bash
npx cap init "Forge" "com.forge.coach" --web-dir=www
```

### 3. Add the Android platform
```bash
npx cap add android
```
This generates an `android/` folder — a real Android Studio project.

### 4. Generate app icons & splash screen
```bash
npx @capacitor/assets generate --android
```
This reads `resources/icon.png` and `resources/splash.png` and creates every size Android needs.

### 5. Sync everything into the native project
```bash
npx cap sync android
```

### 6. Open in Android Studio
```bash
npx cap open android
```
Android Studio launches. Wait for **"Gradle sync"** to finish (bottom status bar). First time can take several minutes.

### 7. Run it on an emulator or your phone
- **Emulator:** In Android Studio, click **Device Manager → Create Device**, pick e.g. Pixel 7, download a system image (API 34), and start it. Then press the green ▶ **Run** button.
- **Your phone:** Enable **Developer Options** (tap *Build Number* 7× in Settings → About), turn on **USB debugging**, plug in via USB, then press ▶ **Run**.

🎉 The app installs and launches. Walk through onboarding and you're live.

> **Whenever you change anything in `www/`**, re-run `npx cap sync android` then ▶ Run again.

---

## Tips & notes

- **Fully offline:** the app loads fonts from Google Fonts. To make it 100% offline (and simplify the data-safety form), download the Fraunces / Manrope / JetBrains Mono font files into `www/fonts/` and replace the `<link>` in `index.html` with a local `@font-face`. Optional.
- **Camera permission:** the `@capacitor/camera` plugin adds the camera permission automatically. The first time a user takes a progress photo, Android asks for permission — that's expected.
- **Notifications:** reminders are scheduled on-device via `@capacitor/local-notifications`. The user enables them in **Coach → Reminders**; Android will prompt for notification permission.
- **iOS:** this same project can target iPhone too — run `npx cap add ios` (requires a Mac with Xcode and an Apple Developer account, $99/yr).
- **Your data persists** between app launches via `@capacitor/preferences` (native secure key-value storage). The **Export all data** button in Settings creates a JSON backup.

---

## ⚠️ Health disclaimer (please keep this in your listing)

Forge gives science-based estimates using standard formulas (Mifflin-St Jeor BMR, activity multipliers, evidence-based macro ranges). It is **not medical advice** and does not replace a doctor or registered dietitian. Users with health conditions, eating-disorder history, or who are pregnant should consult a professional before changing diet or exercise. Consider adding this line to your store description and keeping the in-app disclaimer (already in the Coach tab) intact.

---

Built with care. Now Forge yourself and level up your game. 🔥
