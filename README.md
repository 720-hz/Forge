# 🔥 Forge — Your Daily Coach

A complete, production-ready fitness app that lives entirely on your phone.
Calorie tracking, training plans, and the kind of consistency that actually
changes your body — without selling your data to anyone.

Built with vanilla JavaScript and Capacitor, packaged as a native Android
app. No frameworks, no backend, no accounts. Your data never leaves the
device.

## What it does

- **Smart onboarding** that calculates your real targets using Mifflin-St Jeor
  BMR, activity multipliers, and evidence-based macro splits
- **Daily dashboard** — calorie ring, macros, water, steps, today's workout
- **Food log** — 60+ foods, custom entries, favorites, recents, saveable meals
- **Live workout logger** — log sets/reps/weight in real time with an automatic
  rest timer; pre-fills your last session's weights
- **Auto personal records** with estimated 1-rep max from your logged sets
- **Cardio tracker** — calorie burn from MET values and your body weight
- **Body tracking** — weight chart, measurements, Navy-method body-fat estimate,
  progress photos
- **History** — calendar of every logged day
- **Weekly review** — auto-generated insights and adherence score
- **24 achievements**, reminders, exercise library, JSON data export

## Why

Most fitness apps either sell your data, hide features behind a subscription,
or both. Forge is what a fitness app should be: useful, complete, fast,
private. One person's data, one person's phone, end of story.

## Tech

- Vanilla JS — no React, no framework, no build step
- Capacitor for native Android wrapping
- Native plugins: Camera, Filesystem, Local Notifications, Haptics, Preferences
- Stores all data locally via `@capacitor/preferences`

## Status

v1.0 — fully functional, ready to ship to Google Play. Build instructions
included in the repo (`README.md`).

---

Not medical advice. Calorie and macro estimates use established formulas
A full-featured Android fitness app — calorie tracking, training plans,
live workout logger with rest timer, auto-detected personal records,
cardio, body measurements, progress photos, achievements, and a weekly
review. Built with vanilla JS + Capacitor. 100% offline, all data stays
on the device.
and general best-practice training principles, but they're a starting point,
not a prescription. Consult a doctor or registered dietitian for any
health conditions.
