# Customs Portal – Releases

This repository contains the official releases for **Customs Portal**, a platform for automating Romanian customs declaration workflows. The platform consists of two parts: a **web application** (hosted on Vercel) and a **Windows desktop application** (distributed here).

---

## What is Customs Portal?

Customs Portal helps professionals working with the Romanian customs system automate the downloading of import (DVI) and export (DVE) customs declarations. It eliminates manual, repetitive browser work by running automation in the background and streaming live progress directly in the interface.

### Web Application

The web app is the entry point for users. It handles:

- **Authentication** – user accounts via Clerk
- **Billing & subscriptions** – payment processing via Stripe
- **Download page** – users download the desktop app after signing in
- **Legal pages** – terms, privacy policy, cookies

Users access it from a browser. Once subscribed, they download and install the desktop application.

### Desktop Application

The Windows desktop app is an Electron wrapper around the same Next.js web app, running locally on the user's machine. It provides:

- **Automated DVI downloads** – imports customs declarations for a selected date
- **Automated DVE downloads** – exports customs declarations for a selected date
- **Live log streaming** – real-time progress during automation runs
- **Resume from last position** – if a run is interrupted, it resumes from the last saved page and row
- **Auto-updates** – checks for new versions on every launch and updates automatically

The app runs locally and connects to the user's VPN to access the customs system.

---

## Installation

1. Download the latest installer from the [Releases](../../releases/latest) page
2. Run `Customs-Portal-Setup-x.x.x.exe`
3. Follow the on-screen instructions
4. Launch **Customs Portal** from the desktop shortcut
5. Sign in with your account and start using DVI/DVE automation

## System Requirements

- Windows 10 or later
- Active Customs Portal subscription
- VPN connection to the customs network

## Updates

Updates are delivered automatically. When a new version is available, the application will notify you and install it on the next restart. No manual download needed.

---

## For maintainers – How to publish a new release

1. Make your changes in the `customs-portal-electron` project
2. Bump the version in `package.json` (e.g. `"version": "1.0.1"`)
3. Run the build and publish command:
   ```powershell
   $env:GH_TOKEN = "ghp_yourtoken"
   npm run build -- --publish always
   ```
4. Go to [Releases](https://github.com/laurentiucozma12/customs-portal-releases/releases)
5. Click the pencil icon on the new Draft → scroll down → **Publish release**

All users with the app installed will receive the update automatically on next launch.

### Download link for the site

Always points to the latest release — update the version number after each release:

```
https://github.com/laurentiucozma12/customs-portal-releases/releases/latest/download/Customs-Portal-Setup-x.x.x.exe
```
