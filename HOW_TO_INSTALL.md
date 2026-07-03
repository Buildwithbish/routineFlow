# 🌊 RoutineFlow Pro — Setup Guide

Your personal life OS: routine planner, Instagram-style profile, Hevy-style fitness tracker, AI calorie logger, and Coach Bish (your AI trainer).

---

## ⚡ Quick start (30 seconds)

1. **Download** `RoutineFlow.html` to your laptop (e.g. into a folder called `RoutineFlow`)
2. **Double-click** the file — it opens in your browser
3. Done. That's the whole app. No server, no npm, nothing to build.

---

## 🖥️ Install it like a real desktop app (recommended)

This gives you an app icon, its own window (no browser tabs), and a Start Menu / Dock entry.

### Chrome or Edge:
1. Open `RoutineFlow.html` in Chrome or Edge
2. Click the **⋮ menu** (top-right)
3. Choose **Cast, save and share → Install page as app…** (Chrome) or **Apps → Install this site as an app** (Edge)
4. Name it **RoutineFlow** and click Install
5. It now appears in your Start Menu (Windows) or Applications (Mac). Pin it to your taskbar/dock!

---

## 📂 Set it up with VS Code + GitHub (your workflow)

Since you have VS Code and GitHub installed, here's the professional way to keep it versioned and safe:

### Step 1 — Create a project folder
```bash
mkdir RoutineFlow
cd RoutineFlow
```
Move `RoutineFlow.html` into this folder.

### Step 2 — Open in VS Code
```bash
code .
```
Or: open VS Code → File → Open Folder → select `RoutineFlow`

### Step 3 — Initialize Git
Open the VS Code terminal (`Ctrl + ~`) and run:
```bash
git init
git add RoutineFlow.html
git commit -m "Initial commit: RoutineFlow Pro v3"
```

### Step 4 — Push to GitHub
1. Go to https://github.com/new
2. Name it `routineflow` → Create repository (keep it **Private** — it's your personal data app)
3. Back in the VS Code terminal:
```bash
git remote add origin https://github.com/YOUR_USERNAME/routineflow.git
git branch -M main
git push -u origin main
```

### Step 5 — Preview while editing (optional)
Install the **Live Server** extension in VS Code:
1. Extensions panel (`Ctrl+Shift+X`) → search "Live Server" → Install
2. Right-click `RoutineFlow.html` → **Open with Live Server**
3. Now the browser auto-refreshes whenever you edit the file

---

## 🤖 Important: AI features

The AI features (**Coach Bish chat**, **AI food logger**, **screenshot import**) call the Claude API. They work automatically when the app runs **inside Claude's artifact environment** (claude.ai).

When you run the file **locally on your laptop**, the AI calls need an Anthropic API key. Two options:

**Option A (easiest):** Use the app inside claude.ai as an Artifact — all AI features work with zero setup.

**Option B (local):** Get an API key from https://console.anthropic.com, then in `RoutineFlow.html` find the three `fetch("https://api.anthropic.com/v1/messages"` calls and add to the headers:
```js
"x-api-key": "YOUR_API_KEY",
"anthropic-version": "2023-06-01",
"anthropic-dangerous-direct-browser-access": "true"
```
⚠️ Never commit your API key to GitHub. Everything else (planner, fitness, habits, photos, journal) works 100% offline.

---

## 💾 Where's my data?

Everything is saved in your browser's localStorage — private to your machine. Nothing is uploaded anywhere.

⚠️ **Tip:** Data is tied to the browser + file location. If you move the file, use the same browser to keep your data.

---

## ✨ Feature guide

| Section | What it does |
|---|---|
| **My Routine** (big blue button) | Day / Week / Month planner — Google Calendar style. Your KOI classes (ICT728, 731, 734, 762) are pre-loaded |
| **Profile** | Instagram-style profile — avatar, bio, stats, progress photo grid |
| **Fitness** | Hevy-style workout tracker — templates, sets×reps×weight, PRs, history |
| **Nutrition** | MyFitnessPal-style — type "2 eggs and toast" and AI estimates macros |
| **Habits** | Streak tracking with 7-day grids |
| **Coach Bish** | Your AI trainer — ask about fitness, wellbeing, your daily routine. He sees your real data |
| **AI Import** | Upload a screenshot of your roster/timetable → auto-adds to your routine |
| **Journal** | Daily reflections with writing prompts |
| **Analytics** | 30-day activity charts and habit consistency |

### Keyboard shortcuts
- `Ctrl/Cmd + N` — new task
- `Ctrl/Cmd + K` — jump to Coach Bish
- `Esc` — close any popup
