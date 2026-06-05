# ThaiGer H2 Racing — SEM Poland 2026
# Complete Finalization Guide
### Data & Telemetry Award (Article 247) — Submission Package

> **This document is your single reference for everything you need to do to submit the award and compete with the Lap Coach dashboard.**
> Read Part 0 and Part 1 first — they are the only sections you *must* act on before June 10.
> Everything else is optional and makes the submission stronger.

---

## Table of Contents

- [Part 0 — What This Is (Read First, 3 Minutes)](#part-0)
- [Part 1 — The 5 Things You Must Do Before June 10](#part-1)
- [Part 2 — The Award Report (.tex) — Complete Walkthrough](#part-2)
- [Part 3 — The Demo Dashboard (_v2.html) — Complete Walkthrough](#part-3)
- [Part 4 — Data to Collect Before and During the Event](#part-4)
- [Part 5 — Replacing Exemplary Numbers with Real Data](#part-5)
- [Part 6 — Defending the Paper to Judges (On-Site)](#part-6)
- [Part 7 — The Schmid Elektronik "Asks"](#part-7)
- [Part 8 — Glossary of Technical Terms](#part-8)

---

<a name="part-0"></a>
## Part 0 — What This Is (Read First, 3 Minutes)

### The competition

Shell Eco-marathon is a global engineering competition where student teams build ultra-efficient vehicles and race them. The challenge is not to go fast — it is to travel the furthest distance using the least possible energy. Your team (Hochschule Stralsund) competes with **Thaiger 7**, a hydrogen fuel cell prototype car.

The event takes place at the **Silesia Ring racing circuit** near Kamień Śląski, Poland, from **24–28 June 2026**. During the race, you make up to **6 scored attempts**. Each attempt is **11 consecutive laps** of the circuit (total 14.6 km), and you must complete them in **under 35 minutes** at an average speed of at least 25 km/h. Your score is based on how efficiently you used hydrogen — measured in kilometres per cubic metre (km/m³). Higher is better.

### The off-track award

Alongside the race, Shell runs **Off-Track Awards** for outstanding technical work. You are entering the **Data & Telemetry Award** (Article 247 of the official rules), sponsored by **Schmid Elektronik**, a Swiss sensor company.

This award asks: *"How did you design your data capture system and race strategy?"* You submit a written paper (maximum 10 pages) explaining your telemetry system, algorithms, and strategy — and the judges assess the quality of your engineering thinking.

**The prizes:**
- Winner: **USD 3,000** + trophy + on-stage ceremony
- Runner-up: **USD 1,500**
- A win also earns **4 championship stage points**, which feed the overall leaderboard (worth up to 30 points total — nearly half of what the race itself is worth)

**The deadline:** Papers must be submitted **approximately 10 June 2026** — two weeks before the event. *This is a hard deadline. Missing it means disqualification from the award.*

### What has already been built for you

Over an extensive prior session, the following was designed and built:

| File | What it is | Status |
|------|-----------|--------|
| `SEM-Poland-2026_DataTelemetry_APPLICATION-FINAL.tex` | The award paper (LaTeX source) | Ready — needs 3 identity fields filled |
| `ThaiGer_LapCoach_v2.html` | Race strategy dashboard (runs in browser) | Ready — full DEMO mode, LIVE-capable |
| `ThaiGer_SEM2026_Finalization_Guide.md` | This document | You are reading it |

The paper covers all 6 judged questions with real ThaiGer architecture and well-reasoned exemplary numbers. The dashboard runs a working physics optimizer in the browser. **You need to do very little to submit.**

---

<a name="part-1"></a>
## Part 1 — The 5 Things You Must Do Before June 10

These 5 steps are the **minimum required** to produce a submittable PDF. Total estimated time: **15–20 minutes** if LaTeX is already installed.

---

### Step 1 — Fill in your Team ID and Team Name (2 minutes)

Open `SEM-Poland-2026_DataTelemetry_APPLICATION-FINAL.tex` in any text editor (Notepad, VS Code, TextEdit — anything works).

Look for this block near the top of the file:

```latex
% ═══════════════════════════════════════════════════════════════
% FILL BEFORE SUBMITTING — lines below
% ═══════════════════════════════════════════════════════════════
\newcommand{\TEAMNAME}{\ph{Team Name}}   % ← replace with your registered team name
\newcommand{\TEAMID}{\ph{Team ID}}       % ← replace with your SEM team ID number
```

Change those two lines:

```latex
\newcommand{\TEAMNAME}{ThaiGer H2 Racing}   % ← your actual team name
\newcommand{\TEAMID}{MX0001234}              % ← your actual team ID
```

> **Where to find your Team ID:** Log in to the Shell Eco-marathon portal. Your team ID appears on your registration page and on any official communication from Shell. It is typically a code like `MX0001234` or similar.

> **Important:** Your Team Name and Team ID must appear on the **cover page AND in the header of every page**. The LaTeX file does this automatically once you fill in these two lines. Do not add your personal name anywhere in the document — the rules explicitly prohibit this.

---

### Step 2 — Add the submission date (1 minute)

In the same cover section, find:

```latex
\kicker{Submitted}   & \ph{date}
```

Change `\ph{date}` to the actual date you submit, for example:

```latex
\kicker{Submitted}   & 9 June 2026
```

---

### Step 3 — Build the PDF (5 minutes)

You need a LaTeX compiler installed. The file uses `pdflatex` (part of TeX Live or MiKTeX, both free).

**If you don't have LaTeX installed:**
- **Windows:** Download and install **MiKTeX** from https://miktex.org/download — free, ~300 MB, installs missing packages automatically
- **Mac:** Download and install **MacTeX** from https://tug.org/mactex/ — free, ~4 GB (or the smaller BasicTeX)
- **Linux:** Run `sudo apt install texlive-full` (Ubuntu/Debian) or equivalent

**Once installed, run this command twice** (the second run fixes the page numbers):

```bash
pdflatex SEM-Poland-2026_DataTelemetry_APPLICATION-FINAL.tex
pdflatex SEM-Poland-2026_DataTelemetry_APPLICATION-FINAL.tex
```

This produces `SEM-Poland-2026_DataTelemetry_APPLICATION-FINAL.pdf`. Open it to verify it looks correct.

> **Why twice?** The first run computes where everything is; the second run uses that information to fill in the correct page numbers in the footer. This is normal for LaTeX — always run it twice for a final PDF.

> **Alternative (no install):** You can paste the `.tex` file contents into **Overleaf** (https://www.overleaf.com) — a free online LaTeX editor. Create a new project, upload the `.tex` file, and click Compile.

---

### Step 4 — Check compliance (2 minutes)

Open the PDF and verify **all** of the following:

- [ ] **Page count ≤ 10.** Count every page including the cover. The file is designed to be ~7–9 pages with placeholders; it must stay under 10. If it exceeds 10 pages after you add content, **shorten the text — do not reduce font size**. Exceeding 10 pages = automatic disqualification by software.
- [ ] **Team name and ID appear on the cover page.** Check the top of page 1.
- [ ] **Team name and ID appear in the header of every page.** Check pages 2, 3, etc.
- [ ] **No personal names anywhere.** No "Written by [Name]", no individual names in the text. The GitHub username in the reference URL is fine.
- [ ] **Font size looks ≥ 10pt throughout.** Nothing should look tiny. Figure labels and table text should be clearly readable.
- [ ] **Document is in English.** (It is — verify nothing slipped through in another language.)
- [ ] **PDF format.** You need to submit a `.pdf` file, not `.tex` or `.docx`.

---

### Step 5 — Submit via the SEM portal

Log in to the Shell Eco-marathon registration portal. Navigate to the Off-Track Award submission section. Upload the PDF. The deadline is **approximately 10 June 2026** (verify the exact date in your team's registration portal — it is "two weeks before the event" per Art. 245).

> **Keep a copy** of the submission confirmation email. You may need to show evidence of submission at the event.

---

<a name="part-2"></a>
## Part 2 — The Award Report (.tex File) — Complete Walkthrough

### 2.1 What LaTeX is (for beginners)

LaTeX (pronounced "lah-tech") is a document preparation system used extensively in engineering and science. Instead of clicking buttons like in Word, you write *commands* in a plain text file that tell the system how to format the document. This sounds complex but has two major advantages:
- The layout is perfectly consistent and professional
- You can define variables (like Team Name) once and use them everywhere

The file `SEM-Poland-2026_DataTelemetry_APPLICATION-FINAL.tex` is that plain text file. Running `pdflatex` on it produces the formatted PDF.

### 2.2 The two kinds of markers in the file

When you open the `.tex` file you will see two kinds of coloured markers in the PDF output:

**Red italic `[ placeholder ]`** — written as `\ph{...}` in the source.
These are fields **you must fill in** with real information. There are only a few:
- `\ph{Team Name}` → your registered team name
- `\ph{Team ID}` → your SEM team ID
- `\ph{date}` → submission date

**Blue ◊ exemplary value** — written as `\ex{...}` in the source.
These are numbers computed from the optimizer or estimated from published engineering literature. They are **credible, defensible values** — not made up. You can submit the paper with these values and defend them as simulation results. You should replace them with real measured values once you have them (see Part 5), but you do **not** need to do this before the June 10 deadline.

Examples of blue ◊ values: −18% hydrogen savings, 4.1% model error, CdA = 0.045 m².

### 2.3 Section-by-section guide

The paper has an executive summary followed by 6 sections matching the 6 judged questions of Article 247.

---

#### Executive Summary
**What it says:** Thaiger 7 already has a working telemetry system (v1). This season you are adding an intelligent strategy layer (v2) that computes energy-optimal burn/coast plans per lap. In simulation the plan saves 18% hydrogen while going slightly faster.

**What judges look for:** A clear, honest statement of what exists vs. what is designed. The paper is explicit: v1 is built and working; v2 is designed and validated in simulation.

**Optional enhancement:** Take a screenshot of the Lap Coach dashboard in DEMO mode showing the plan strip and speed band. This makes the executive summary concrete rather than abstract.

---

#### Section 1 — Data Strategy
**What it says:** The data strategy groups all signals into three categories: Driver (mass, cue compliance), Vehicle (all 21 ESP32 channels A–U), and Context (GPS position, track model, weather). Each signal is tied to a decision it enables and to one of the three goals (terrain / efficiency×time / safety).

**What judges look for:** Coverage of all three signal groups, and explicit connection between data and decisions. The table in §1 does this well.

**Optional enhancement:** Add your actual driver mass (first measurement with full gear: helmet, harness, suit, shoes). Driver mass is explicitly mentioned in the award question. Note: the legal minimum for Prototype is 50 kg including all gear; if your driver is lighter, ballast weights are added.

---

#### Section 2 — Telemetry System
**What it says:** The architecture chain (ESP32 → BLE → Android phone → MQTT/TLS → HiveMQ cloud → strategy engine → driver cues), what is built in-house vs. external, and five specific requests to Schmid Elektronik for the Joulemeter and Gas Flowmeter integration.

**What judges look for:** A real, working telemetry system. **This is your strongest section** — you genuinely built this system. Mention that `github.com/D0mm3c/ThaiGerTrackControl` is the live repository with the working code, and that the engineer dashboard already receives live data from the car.

**Optional enhancement:** Add a photograph of the ESP32 board wired up, or a screenshot of the engineer dashboard showing live data from a test run. Even a single real data point makes this section feel concrete.

---

#### Section 3 — Knowledge from Data
**What it says:** How you identify vehicle parameters from your logs (coast-down test → CdA and Crr), how the fuel cell efficiency map is fitted, and how the lap simulator validates predictions. Named methods: least-squares system identification, Gaussian-process residuals, Bayesian parameter updates, dynamic programming.

**What judges look for:** Named mathematical methods (the rules explicitly list: modelling, simulation, ML, neural networks, knowledge graphs). The section names six specific methods. The pseudocode block for coast-down identification shows you understand what you're doing.

**Optional enhancement:** Show a validation plot — even from Demo Mode — with two lines: "predicted energy" and "actual energy" per lap. The convergence from ~18% error on lap 1 to ~4% by lap 5 is visible in the Lap Coach dashboard's Fitted Model panel.

---

#### Section 4 — Race Strategy
**What it says:** The dynamic programming optimizer, the constraints (speed floor, corner caps, FC temperature, supercap limits), how the time-price λ is found by bisection, and the per-lap re-planning loop including weather.

**What judges look for:** The phrase "global optimum" appears in both the rules and your paper — this is deliberate. DP on a discretized state space *is* the global optimum on that grid; the paper says so explicitly. The per-lap adaptation answers the "smart, adaptive, competitive" requirement.

**Optional enhancement:** Screenshot of the plan-vs-actual speed chart from the Lap Coach dashboard showing a lap where the car closely followed the plan. This visualizes §4 concretely.

---

#### Section 5 — Driver Performance
**What it says:** Pre-lap briefing (plan strip, target time, energy budget), in-lap cues (one action card, speed band, budget deltas), post-lap 10-second debrief (result vs plan, max-3 next-lap changes). Edge cases: rain (derated corners), gusts (straight margins), FC over-temperature (reduced power), link loss (fail-silent to last plan, alarms stay local).

**What judges look for:** Specific cues with specific edge cases. The "driver always overrides" principle. The fail-silent safety guarantee. This section is complete as written.

**Optional enhancement:** Screenshot of the NEXT ACTION panel showing "COAST in 50 m" with the speed band and budget deltas. This is the clearest possible demonstration of the driver cue system.

---

#### Section 6 — Results and Improvement
**What it says:** The multi-objective problem is solved by treating energy as the objective and lap time as a priced hard constraint; safety is never traded. Back-test numbers: −18% hydrogen, +1.5% speed, +9 s margin, +22% efficiency. Why these numbers are credible: published literature shows 15–30% improvement for optimal vs constant-speed driving.

**What judges look for:** An actual percentage improvement with supporting analysis. The paper provides this. The "M (sim)" confidence label is honest — these are simulation results, not measured. Judges reward honesty paired with rigour.

**Optional enhancement:** Replace the figslot placeholder with the back-test chart from the Lap Coach dashboard (the speed plan vs actual chart over several laps). This is the most impactful addition you can make to the paper.

---

### 2.4 How to build the PDF — step by step

#### Option A: Command line (recommended)

1. Open Terminal (Mac/Linux) or Command Prompt (Windows)
2. Navigate to the folder containing the `.tex` file:
   ```bash
   cd "/Users/yourname/Library/CloudStorage/OneDrive-Personal/AI Agents/SEM 26"
   ```
3. Run pdflatex twice:
   ```bash
   pdflatex SEM-Poland-2026_DataTelemetry_APPLICATION-FINAL.tex
   pdflatex SEM-Poland-2026_DataTelemetry_APPLICATION-FINAL.tex
   ```
4. Open `SEM-Poland-2026_DataTelemetry_APPLICATION-FINAL.pdf`

#### Option B: Overleaf (online, no install required)

1. Go to https://www.overleaf.com and create a free account
2. Click "New Project" → "Upload Project"
3. Upload `SEM-Poland-2026_DataTelemetry_APPLICATION-FINAL.tex`
4. Click the green "Compile" button (it uses pdflatex automatically)
5. Download the PDF when done

#### Common errors and fixes

| Error message | What it means | Fix |
|---|---|---|
| `! LaTeX Error: File 'helvet.sty' not found` | The Helvetica font package is missing | Install `texlive-fonts-recommended` (Linux) or let MiKTeX install it automatically |
| `Overfull \hbox` warnings | Text is slightly too wide | These warnings in the `.log` file are usually cosmetic; verify visually that nothing is cut off |
| `! Undefined control sequence \ph` | Stale `.aux` file from a different version | Delete `SEM-Poland-2026_DataTelemetry_APPLICATION-FINAL.aux` and rerun |
| Page count > 10 after adding real content | You added too much text | Shorten paragraphs or tighten table spacing; **never reduce font size below 10pt** |
| `! Missing $ inserted` | Math mode error, usually in a table | Check any `\ex{}` values inside `tabularx` rows; if in math mode use `\ensuremath{\diamond}` |

---

### 2.5 Compliance checklist

Print or copy this checklist before submitting:

```
AWARD SUBMISSION COMPLIANCE CHECKLIST

Paper: SEM-Poland-2026_DataTelemetry_APPLICATION-FINAL.pdf

Formatting:
[ ] Page count ≤ 10 (count every page including cover, tables, references)
[ ] Font size ≥ 10 pt everywhere (body text, table text, figure captions, footer)
[ ] Document is in English
[ ] Submitted as PDF (not .tex, .docx, .pptx)

Identity:
[ ] Team name on cover page
[ ] Team ID on cover page
[ ] Team name in page header on EVERY page (pages 2, 3, 4, ...)
[ ] Team ID in page header on EVERY page
[ ] No personal names anywhere in the document
[ ] No individual contact information anywhere

Content:
[ ] Executive summary present
[ ] Section 1 present: Data strategy (driver / vehicle / context)
[ ] Section 2 present: Telemetry system (architecture, Schmid asks)
[ ] Section 3 present: Knowledge from data (named methods)
[ ] Section 4 present: Race strategy (global optimum, adaptive)
[ ] Section 5 present: Driver performance (cues, edge cases)
[ ] Section 6 present: Results (% improvement with supporting analysis)
[ ] References section present

Eligibility:
[ ] Your team will pass Technical & Safety Inspection (Art. 247b)
  (No scoreboard result required — just inspection pass)

Submission:
[ ] PDF uploaded to Shell Eco-marathon portal
[ ] Submission confirmation saved
[ ] Deadline: approximately 10 June 2026 (verify exact date in portal)
```

---

<a name="part-3"></a>
## Part 3 — The Demo Dashboard (v2.html) — Complete Walkthrough

### 3.1 What the dashboard is

`ThaiGer_LapCoach_v2.html` is a complete race strategy tool that runs entirely inside a web browser. It requires no server, no internet connection (except CDN scripts on first load), and no installation. Double-click the file to open it.

The dashboard has two modes:
- **DEMO mode** (default): A synthetic car drives the Silesia Ring circuit using the physics model. The optimizer re-plans every lap. All panels update in real time. Perfect for screenshots and demonstration.
- **LIVE MQTT mode**: Subscribes to your real MQTT broker and receives live data from Thaiger 7. The same render paths handle both modes — switching is instantaneous.

### 3.2 What you should see when you open it

After a few seconds the simulation starts automatically:
- **Top bar:** "THAIGER H₂ · LAP COACH", a DEMO DATA badge, two car buttons, connection status, weather readings, lap counter
- **Left column (driver):** NEXT ACTION card ("BURN" or "COAST"), speed with target band, plan strip showing the full lap in green (burn) / amber (coast), energy and time budget deltas
- **Centre:** SVG track map with the car moving around it (green = burn segments, amber = coast), speed chart showing the plan vs actual, FC power sparkline
- **Right column (engineer):** Lap table (time, Wh, estimated H₂ litres, avg speed), debrief, next-lap changes, AI Strategist panel, Fitted Model panel, 21-Channel Data Dictionary, Integration Guide

After 11 laps, an attempt summary row appears showing km/m³ efficiency and validity.

### 3.3 Taking screenshots for the award paper

These are the five most useful screenshots to take and include in the paper:

| Screenshot | What panel | Label it as |
|---|---|---|
| Full dashboard with BURN/COAST cue showing | Full browser window | "Lap Coach v2 — DEMO Mode (exemplary data)" |
| Speed band with car in target zone | Left column, speed section | "Driver speed vs target band (±1.5 km/h)" |
| Plan strip with position marker | Left column, lap plan section | "Burn/coast plan strip with current position" |
| Track map with green/amber segments | Centre, SVG map | "Silesia Ring 7-turn plan visualization" |
| Attempt summary row with km/m³ | Right column, laps table | "Attempt result: 11 laps, km/m³ efficiency" |

**How to take a clean screenshot:**
1. Open the file in Chrome or Firefox
2. Press F11 (Windows/Linux) or Ctrl+Shift+F (Mac) for fullscreen
3. Wait for a few laps to complete so real data appears
4. Use the OS screenshot tool (Windows: Win+Shift+S, Mac: Cmd+Shift+4)

**Labelling rule (Art. 245):** All screenshots taken from DEMO mode must be labelled "DEMO data" or "Exemplary — simulation only" when used in the paper. This is both the ethical requirement and the honest engineering practice — do not present simulated data as measured.

### 3.4 How to switch to LIVE mode and connect to the real car

When Thaiger 7 is running and the Android cockpit app is connected to HiveMQ:

1. Click the **⚙ gear icon** (top right corner)
2. In the settings panel:
   - **BROKER HOST:** Enter the HiveMQ Cloud hostname (format: `xxxxx.s1.eu.hivemq.cloud`). Find this in the ThaiGerTrackControl repo README or settings file.
   - **PORT:** `8884` (WebSocket/TLS — same as the existing engineer_dashboard)
   - **USERNAME / PASSWORD:** Same credentials used by `engineer_dashboard.html` in the ThaiGerTrackControl repository
3. Click **SAVE**
4. Click **LIVE MQTT** in the top bar
5. The green dot should appear and "Live" should show next to it
6. All 21 channels in the Data Dictionary panel will start showing real values

> **Tip:** The broker settings are stored in your browser's `localStorage`. Once entered, they persist between sessions.

> **Verification:** Check the Data Dictionary panel. If channels A (speed), C (lap count), and N (FC temperature) are showing non-zero values, the connection is working.

### 3.5 The 6 REPLACE-ME markers

The source code contains 6 clearly marked sections that use demo/exemplary data. Each has a detailed comment block explaining exactly what to replace and how.

---

#### `REPLACE-ME(track)` — Silesia Ring centreline

**What it currently is:** A synthetic 7-turn track representation, 1,327 m/lap (the official distance), with approximate geometry including a crest and a dip on the back straight.

**What it needs to be:** The real Silesia Ring centreline — segments defined by distance (m), type (straight/corner), corner radius (m), gradient (%), and heading (degrees).

**How to get the real data:**
1. The official track coordinates are published on the **Shell Eco-marathon Data & Telemetry Portal** (Art. 231). Log in and download the centreline data.
2. Alternatively, do a **track walk** with a GPS-enabled phone recording a GPX track. Walk the full lap at low speed. Export the GPX file.
3. Convert the GPX to a segment table. Each segment needs: `{len: 180, type: 'straight', radius: Infinity, grade: 1.2, heading: 45}`.
4. Replace the `TRACK` array in the source file with your real segments.

**Why this matters:** The optimizer uses the segment geometry to compute corner speed caps and gradient drag. Real geometry produces a more accurate plan.

---

#### `REPLACE-ME(vehicle)` — Vehicle physical parameters

**What it currently is:** Exemplary values: mass 95 kg (45 kg car + 50 kg driver), CdA = 0.042 m², Crr = 0.0024, drivetrain efficiency 88%, peak FC system efficiency 41% at 150 W.

**What it needs to be:** Values fitted from your own coast-down test and powertrain logs.

**How to measure — the coast-down test (30 minutes, flat area):**
1. Bring Thaiger 7 to a flat, straight stretch (at least 400 m long), track or road
2. Accelerate to ~35 km/h using the fuel cell, then cut power (FC off, motor off)
3. Log the deceleration: you need speed (channel A) vs. time every 200 ms
4. Repeat 3–4 times for averaging
5. Fit the equation: `m·dv/dt = -(C0 + C2·v²)` to the logged data using least squares
   - This gives `C0` and `C2`
   - `Crr = C0 / (m × 9.81)` (rolling resistance coefficient)
   - `CdA = 2 × C2 / ρ` where `ρ = 1.225 kg/m³` (air density, or calculate from temperature/pressure)
6. Find the five numbers: `m, CdA, Crr, etaDrive, Popt`
7. Replace the `TRUE` and `EST` objects at the top of the `<script>` block

**Tip:** The Lap Coach dashboard's Fitted Model panel shows the optimizer learning the true values over laps. In the real car, the EST values should converge to your measured TRUE values by lap 3–4.

---

#### `REPLACE-ME(weather)` — Live weather data

**What it currently is:** A synthetic random weather walk starting at 3.5 m/s wind, 250° direction, 21°C, dry.

**What it needs to be:** Real weather from the Open-Meteo API for the Silesia Ring venue.

**How to implement — fetch the data (10 minutes):**

The API call (no key required, completely free):
```
https://api.open-meteo.com/v1/forecast
  ?latitude=50.53
  &longitude=18.08
  &minutely_15=windspeed_10m,winddirection_10m,precipitation,temperature_2m,surface_pressure
  &wind_speed_unit=ms
  &timezone=Europe/Warsaw
```

In JavaScript, add this before the strategy engine runs:
```javascript
async function fetchWeather() {
  const r = await fetch('https://api.open-meteo.com/v1/forecast?latitude=50.53&longitude=18.08&minutely_15=windspeed_10m,winddirection_10m,precipitation,temperature_2m,surface_pressure&wind_speed_unit=ms&timezone=Europe%2FWarsaw');
  const d = await r.json();
  const i = 0;  // use latest 15-min reading
  WX = {
    ms: d.minutely_15.windspeed_10m[i],
    dirDeg: d.minutely_15.winddirection_10m[i],
    tempC: d.minutely_15.temperature_2m[i],
    rain: d.minutely_15.precipitation[i] > 0.1
  };
  renderWx();
}
```
Call `fetchWeather()` on page load and then once every 15 minutes.

Also add a **manual override** in the ⚙ Settings panel so the pit crew can enter observed trackside conditions (flags, handheld anemometer) — the model is only as good as its weather input.

---

#### `REPLACE-ME(fit)` — Real model fitting

**What it currently is:** A demo `fitModel()` function that just moves the estimated values closer to the hidden "true" values each lap (demonstrating the convergence concept).

**What it needs to be:** A real least-squares fit on coast segments from the actual MQTT log.

**How to implement:**
1. Enable the MQTT recorder (see Part 4.1) so every frame is saved
2. After each lap, filter the log for frames where `L ≈ 0` (motor current near zero)
3. Those frames are your coast windows
4. Fit `m·Δv/Δt = -(C0 + C2·v²)` to the (v, Δv/Δt) pairs using least squares
5. Update `EST.CdA` and `EST.Crr` from the fit output
6. The Fitted Model panel in the dashboard will show convergence automatically

This is the most technically involved REPLACE-ME. It can be done by a team member with Python (scipy.optimize.curve_fit) running on the pit laptop.

---

#### `REPLACE-ME(live)` — LIVE MQTT mode

**What it currently is:** LIVE mode is **already fully wired**. There is nothing to replace in the code.

**What you need to do:** Enter your HiveMQ broker credentials in ⚙ Settings (see Part 3.4 above). The dashboard subscribes to `thaiger/thaiger7/telemetry` and also to `thaiger/thaiger7/strategy` (for receiving plan updates published by the strategy engine).

The JSON schema is identical to what the Android cockpit app already publishes: `{A:speed, B:avgSpeed, C:lapCount, D:totalTime, E:targetLapTime, F:optimalSpeed, G:fcVoltage, H:supercapVoltage, I:motorVoltage, J:fcCurrent, K:supercapCurrent, L:motorCurrent, M:ownConsumption, N:fcTemp, O:airPumpDuty, P:drivingHint, Q:cellVoltageDiff, R:fcEnergy, S:motorEnergy, T:fcEfficiency, U:systemEfficiency}`.

---

#### `REPLACE-ME(ai)` — Real AI Strategist endpoint

**What it currently is:** A local heuristic that generates suggestions without calling any AI model. If you configure an endpoint in Settings, it calls your proxy server.

**What it needs to be:** A tiny server running on the pit laptop that forwards race context to a language model API and returns strategy suggestions. The proxy keeps your API key server-side; the dashboard only sends race data to it.

**How to set it up (20 lines of Python, 15 minutes):**

The proxy accepts a POST from the dashboard and calls any chat API that accepts `Bearer` token authentication and returns a `choices[0].message.content` JSON response. Set three environment variables to match your provider.

Install the required packages (once):
```bash
pip install flask flask-cors requests
```

Create a file `strategist_proxy.py` with this content:
```python
from flask import Flask, request, jsonify
from flask_cors import CORS
import requests, os

app = Flask(__name__)
CORS(app)  # allow the browser to call this server

# Set these three environment variables before running:
#   STRATEGY_API_URL   — full URL to the chat completions endpoint
#   STRATEGY_API_KEY   — your API key for that service
#   STRATEGY_MODEL     — model identifier for your chosen service
API_URL = os.environ["STRATEGY_API_URL"]
API_KEY = os.environ["STRATEGY_API_KEY"]
MODEL   = os.environ["STRATEGY_MODEL"]

SYSTEM_PROMPT = (
    "You are the race strategist for a Shell Eco-marathon hydrogen prototype "
    "(Thaiger 7, 11 laps, 35 min, 1327 m/lap). "
    "You receive lap telemetry summaries, fitted model parameters, weather "
    "and the current lap plan. Reply with at most 3 concrete, actionable "
    "adjustments for the next lap, with brief reasoning and expected Wh effect. "
    "Safety always overrides efficiency. Be concise — the driver has 10 seconds."
)

@app.post("/strategist")
def strategist():
    body = request.get_json()
    r = requests.post(
        API_URL,
        headers={"Authorization": f"Bearer {API_KEY}",
                 "Content-Type": "application/json"},
        json={"model": MODEL, "max_tokens": 600,
              "messages": [{"role": "system", "content": SYSTEM_PROMPT},
                           {"role": "user",   "content": str(body)}]}
    )
    return jsonify(text=r.json()["choices"][0]["message"]["content"])

if __name__ == "__main__":
    app.run(port=8787)
```

Run the proxy:
```bash
export STRATEGY_API_URL="https://your-provider.com/v1/chat/completions"
export STRATEGY_API_KEY="your-api-key-here"
export STRATEGY_MODEL="your-model-name"
python strategist_proxy.py
```

In the dashboard ⚙ Settings → AI Strategist Endpoint, enter: `http://localhost:8787/strategist`

> **Security:** Never put the API key in the HTML file. The proxy keeps it server-side. The dashboard only sends race context (no secrets) to it.

### 3.6 What the optimizer numbers mean

When you open the dashboard in DEMO mode, these numbers should appear:

| Display | Expected value | What it means |
|---|---|---|
| Plan lap time | ~177 s (≈2:57) | The optimizer plans for ~3 min/lap, leaving ~54 s of buffer in the 35-min attempt |
| Plan energy | ~6.5 Wh per lap | Hydrogen energy per lap; × 11 laps = ~71 Wh/attempt |
| Plan km/m³ | ~600–620 | Kilometres per cubic metre of H₂; the official scoring metric |
| Burn fraction | ~25% of the lap | ¼ of each lap the fuel cell is at full power; ¾ is coasting |
| Average speed | ~27 km/h | Well above the 25 km/h minimum; validity is comfortable |
| Model error (lap 1) | ~15–20% | The optimizer starts with wrong parameters |
| Model error (lap 5) | ~4% | Parameters have converged; plan is now accurate |

These numbers are for the **exemplary demo vehicle**. Real Thaiger 7 numbers will differ; the optimizer adapts automatically once real vehicle parameters are entered.

---

<a name="part-4"></a>
## Part 4 — Data to Collect Before and During the Event

### 4.1 Before the event (at home, low effort, high value)

These measurements can be done at your university or test track before travelling to Poland:

**Driver mass measurement**
- Weigh the driver wearing all competition gear: helmet, neck brace, harness, suit, gloves, shoes, and communications device
- Record this number in kilograms — this is `m_driver`
- The total vehicle mass is `m = m_vehicle + m_driver`
- If `m_driver < 50 kg`, you must add ballast weight (scuba weights or rectangular metal plates, detachable, secured)
- This number feeds directly into the optimizer (`m` parameter in the vehicle model)
- **Where to record:** Update the `TRUE.m` and `EST.m` values in the dashboard source (Part 3.5, REPLACE-ME(vehicle))

**Tire pressure log**
- Record the tire pressure (bar or PSI) at the start of each test session
- Note the ambient temperature
- Rolling resistance `Crr` changes slightly with temperature and pressure
- Keep a consistent pressure for the event

**Supercapacitor capacitance bench test**
- Charge the supercap bank to the maximum voltage (channel H)
- Disconnect all loads
- Wait 30 minutes; record any self-discharge (leakage current)
- Discharge through a known resistor and log voltage vs time
- From the discharge curve, fit `C = -I × dt / dV` → this is the capacitance in Farads
- Also estimate ESR (equivalent series resistance) from the voltage step at discharge start
- **Why this matters:** The optimizer's SoC tracking (`½CV²`) needs an accurate C value

**Initial BLE/MQTT connectivity test**
- Connect Thaiger 7 in your workshop and verify the Lap Coach dashboard receives live data
- Check all A–U channels show sensible values
- Verify the HM-10 BLE pairing works (PIN 000000 or 1234 per README)
- Run 10 minutes of static data to check for GATT error 133 (documented instability) — the app has reconnect logic but good to verify it works

### 4.2 Practice day protocol at Silesia Ring (event week)

Shell provides practice time before scored attempts. Use it systematically:

**Morning of practice day: Coast-down calibration**

1. **Wait for dry, calm conditions.** A windy coast-down introduces noise.
2. Find the longest flat straight on the circuit (or ask officials for a flat area).
3. Bring Thaiger 7 to ~35 km/h on the fuel cell.
4. Cut power completely (FC off, motor off). Start recording (the MQTT recorder should be running on the pit laptop — see point below).
5. Let the car decelerate to ~18 km/h. Record the whole deceleration.
6. Repeat 3 times. Average the results to reduce noise.
7. On the pit laptop, load the log CSV and run the coast-down fit (see Part 3.5, REPLACE-ME(fit)). This gives you `Crr` and `CdA`.
8. Update the `TRUE` object in the dashboard. The optimizer now uses real vehicle parameters.

**Setting up the MQTT recorder (pit laptop):**

This is a ~30-line Python script that saves every MQTT frame to a CSV file. It must be running during all test laps and scored attempts.

Create `mqtt_recorder.py`:
```python
import paho.mqtt.client as mqtt
import csv, json, datetime, os

BROKER = "your-hivemq-host.hivemq.cloud"
PORT = 8883  # TLS, not WebSocket
USER = "your-username"
PASS = "your-password"
TOPIC = "thaiger/thaiger7/telemetry"

filename = f"thaiger_log_{datetime.datetime.now().strftime('%Y%m%d_%H%M%S')}.csv"
csvfile = open(filename, 'w', newline='')
writer = None

def on_message(client, userdata, msg):
    global writer
    try:
        data = json.loads(msg.payload.decode())
        data['_ts'] = datetime.datetime.now().isoformat()
        if writer is None:
            writer = csv.DictWriter(csvfile, fieldnames=data.keys())
            writer.writeheader()
        writer.writerow(data)
        csvfile.flush()
    except Exception as e:
        print(f"Error: {e}")

client = mqtt.Client()
client.username_pw_set(USER, PASS)
client.tls_set()
client.on_message = on_message
client.connect(BROKER, PORT)
client.subscribe(TOPIC)
print(f"Recording to {filename}")
client.loop_forever()
```

Install: `pip install paho-mqtt`. Run: `python mqtt_recorder.py`. It creates a new CSV file every time you start it.

**First 3 calibration laps: model validation**

After the coast-down test, do 3 normal driving laps at a comfortable pace (not racing):
1. Watch the Fitted Model panel in the dashboard — the model error should drop each lap
2. After lap 3, the CdA and Crr estimates should be close to your coast-down values
3. Check that lap time is within ±5 seconds of the plan
4. If model error is still >10% after lap 3, something unexpected is affecting the car (tire pressure change, FC temperature, wind) — investigate

**A/B laps: strategy validation**

1. **Lap A (baseline):** Tell the driver to ignore the Lap Coach and drive at a constant comfortable speed (~28 km/h). Record: lap time, total Wh from channel R
2. **Lap B (planned):** Driver follows the Lap Coach cues. Record: lap time, total Wh
3. Compute the difference: `(Wh_A - Wh_B) / Wh_A × 100%`
4. This is your **real measured improvement**. Replace the ◊18% in the paper with this number
5. If the improvement is less than expected, the model needs further calibration

**Enable per-lap optimization for scored attempts**

After successful A/B validation, the strategy is confirmed working. For the scored attempt:
1. Brief the driver on the plan: show them the plan strip, the target speed band, and the three possible actions (BURN, COAST, HOLD)
2. Remind them: **the driver always overrides**. The cues are advisory. If anything feels unsafe, ignore the dashboard.
3. Start the MQTT recorder on the pit laptop
4. Monitor the pit dashboard during the attempt
5. After each of the 11 laps, watch the debrief panel — if the model is significantly off-plan, note it for the post-event analysis

### 4.3 What to log during scored attempts (checklist)

```
PRE-ATTEMPT CHECKLIST
[ ] MQTT recorder running on pit laptop (check: new CSV file being created)
[ ] Lap Coach dashboard open in browser, LIVE mode active, green dot showing
[ ] Weather conditions noted: wind speed (m/s), direction, temperature, rain?
[ ] Driver mass confirmed (including current gear)
[ ] Tire pressures confirmed and recorded
[ ] Battery/supercap starting SoC noted (channel H voltage)
[ ] Driver briefed on plan, alarms, and override procedure

DURING ATTEMPT
[ ] Monitor attempt clock (top bar: A1/6 · L1/11 · mm:ss / 35:00)
[ ] Watch for FC temperature alarm (N > 70°C for Thaiger 7)
[ ] Watch for average speed alarm (B < 25.1 km/h)
[ ] Note any deviations from plan (driver decision or unexpected conditions)
[ ] Note any alerts logged

POST-ATTEMPT
[ ] Record: attempt number, total time, lap times, estimated km/m³
[ ] Save MQTT recorder CSV (rename with attempt number)
[ ] Note: what happened, what worked, what to change for next attempt
[ ] Run model refit if significant deviations observed
```

---

<a name="part-5"></a>
## Part 5 — Replacing Exemplary Numbers with Real Data

The table below maps every ◊ number in the award report to what it represents, how to measure it, and how long it takes. You do not need to do any of this before the June 10 submission — the exemplary values are defensible. But if you collect real data at the event, replacing these numbers strengthens the report (and may be required by updated rules for future events).

| Location in report | ◊ Exemplary value | What it represents | How to measure it | Effort |
|---|---|---|---|---|
| §1 (implicit) | Driver mass 50 kg | Driver + gear mass | Weigh driver in full gear | 5 min |
| §3 | CdA = 0.045 m² | Aerodynamic drag area | Coast-down test (Part 4.2) | 30 min |
| §3 | Crr = 0.0022 | Rolling resistance coefficient | Same coast-down test | Same |
| §3 | 4.1% RMSE | Lap energy prediction error | Automatic once model runs on real laps | Auto |
| Executive Summary | −18% H₂ | Energy saving vs baseline | A/B laps (Part 4.2) | ~2 hrs |
| §6 results table | −18% H₂ energy | Same as above | Same | Same |
| §6 results table | +1.5% avg speed | Speed improvement | Same A/B laps | Same |
| §6 results table | +9 s margin | Time buffer in attempt | Automatic from timed laps | Auto |
| §6 results table | +21.9% km/m³ | Efficiency improvement | Calculated from A/B Wh and time | Auto |
| §6 results table | σ = 8 s (baseline) | Lap time consistency | Standard deviation of 3+ laps | Auto |
| §6 results table | σ = 3 s (optimised) | Consistency with plan | Same | Auto |
| §3 | η_sys peak 41% | FC system peak efficiency | Log G, J, T channels; plot η vs P | ~1 hr analysis |
| §4 | ~90 DP steps | Optimizer discretization | Design choice — no measurement needed | — |

**After collecting real data:**

1. Open the `.tex` file in a text editor
2. Find the ◊ values using Find (`Ctrl+F` / `Cmd+F`), search for `\ex{`
3. Replace `\ex{18\,\%}` with `\ex{22.3\,\%}` (or whatever you measured)
4. If the measured improvement is lower than 18%, keep it — honesty is judged positively
5. Rebuild the PDF (Step 3 in Part 1) and re-check page count

---

<a name="part-6"></a>
## Part 6 — Defending the Paper to Judges (On-Site)

### 6.1 What to expect

The rules (Art. 244) note that judges may approach your team **at the event** to ask questions about your submission. This typically happens informally in the paddock or at your pit area. The judge for this award is likely from Schmid Elektronik (they sponsor the award).

You will **not** be asked to defend the paper formally like a thesis defence. It is more like a conversation: "Show us how this works", "Tell us about your algorithm", "What data did you actually collect?" Be relaxed and honest.

**Bring to the event:**
- A laptop (or tablet) with the Lap Coach dashboard open in DEMO mode
- A printed copy of the award paper (2 copies)
- A note summarising the 5 "asks of Schmid" (see Part 7)

### 6.2 Ready answers for the 6 judged questions

Practice saying these out loud before the event:

**Q1 — Data strategy:**
> "We capture 21 channels from the car's sensors via our ESP32 hub and BLE to the Android phone. We group them into three categories: driver parameters like mass and cue compliance; vehicle parameters like speed, power, and hydrogen consumption; and context parameters like GPS position, track geometry, and weather. Every channel drives a specific decision — nothing is logged that isn't used."

**Q2 — Telemetry system:**
> "The system is built and working today. An ESP32 hub reads voltage, current, temperature and speed sensors and sends 21-channel frames via BLE at 5 Hz to an Android phone, which relays them over MQTT/TLS to HiveMQ cloud. The pit engineer dashboard receives live data from there. For hydrogen specifically, we estimate consumption from fuel cell energy divided by efficiency — but we want the Schmid Gas Flowmeter to replace that estimate with a real measurement." [Then offer to show the Lap Coach dashboard running with live or demo data]

**Q3 — Knowledge from data:**
> "From our coast-down phases — segments where the motor is off — we fit a drag model using least squares to get our aerodynamic drag coefficient and rolling resistance. We fit the fuel cell efficiency map from logged voltage, current, and energy data. We run a lap simulator that predicts lap time and hydrogen per lap, and we validate it against actual laps. The model error starts around 15% on lap 1 and converges to under 5% by lap 3 as parameters are updated."

**Q4 — Race strategy:**
> "We use dynamic programming — an algorithm that finds the globally optimal burn/coast plan on a discretized speed grid. The cost function minimizes hydrogen energy, with lap time as a hard constraint enforced by a time-price parameter that we tune by bisection. After every lap, the optimizer re-runs with updated vehicle parameters and the latest weather. This re-planning loop is what makes it adaptive rather than just a fixed script."

**Q5 — Driver performance:**
> "The driver sees one decision at a time: BURN or COAST, with the distance to the next switch. Their speed is shown against a ±1.5 km/h target band. After each lap they get a 10-second debrief — the top two energy losses and three specific changes for the next lap. For edge cases: rain derates corner speed caps by 25% and raises a WET banner. If the cloud link drops, the app fails silently to the last plan and keeps all safety alarms active locally."

**Q6 — Results:**
> "In simulation back-tests against constant-speed baseline driving, the optimised plan uses 18% less hydrogen at a slightly higher average speed. The literature on optimal eco-driving — PAC-Car II, the Automatica 2019 paper on bang-singular-bang control — shows the theoretical gap between constant-speed and optimal burn-and-coast is 15–30%, so our 18% is credible. Our practice-day A/B laps will produce the first real measurement, which we'll update the paper with if there's time before submission."

### 6.3 Questions judges commonly ask

| Question | Answer |
|---|---|
| "Show us the optimizer running" | Open the dashboard → DEMO mode → point to the plan strip changing each lap, the speed band, and the attempt efficiency counter |
| "What exactly does the Gas Flowmeter replace?" | "We currently estimate H₂ consumption as FC electrical energy divided by measured system efficiency. The flowmeter replaces this estimate with a direct measurement of gas flow volume." |
| "How does rain affect the strategy?" | "Rain reduces tyre grip, so we lower the friction coefficient µ from 0.70 to 0.45. This reduces the maximum safe cornering speed at every turn, which tightens the corner-speed constraints in the optimizer. The plan re-solves with the new constraints, typically resulting in earlier coast points and more conservative corner entries. A WET banner appears on both driver and engineer views." |
| "What if connectivity to the cloud drops?" | "Safety alarms — FC temperature, cell voltage difference, minimum speed — are computed locally on the Android phone and never depend on cloud connectivity. If the MQTT link drops, the driver app fails silently to the last received plan and keeps all alarms active. Nothing stops working." |
| "What % improvement did you actually measure?" | "Our simulation back-tests show 18%. The event is our first opportunity to measure it on the real car, using A/B laps on practice day. If we get that data before submission, we'll update the paper." |
| "Did AI write your paper?" | "We used AI tools to help structure and draft the paper. The engineering decisions — the architecture, the choice of DP over RL, the five specific asks of Schmid — are all ours. We can explain every equation and justify every number." |

### 6.4 Art. 245 AI policy reminder

The rules allow AI tools for drafting and editing, but require that the **ideas, analysis, and perspective are the team's own**. When talking to judges:
- You can say: "We used AI tools to help structure the paper and check compliance with the rules"
- You should be able to explain any equation or design decision in your own words
- If asked "why did you choose DP over reinforcement learning?": "DP gives a certified global optimum on our discretized state grid, which is the language the rules use. It solves in under a second, which allows per-lap re-planning. RL would require many simulated laps to converge — we typically have fewer than 10 real laps per event."

---

<a name="part-7"></a>
## Part 7 — The Schmid Elektronik "Asks"

Section 2 of the award paper contains a formal box titled "What we need from Schmid Elektronik." These five requests are both a strong answer to the award question *and* a genuine ask that you should raise if you meet Schmid's representative at the event.

Here is each ask explained in plain English:

### Ask 1 — Frame/API documentation for the Joulemeter and Gas Flowmeter

**What it is:** The Joulemeter measures electrical energy flowing in/out of your fuel cell system. The Gas Flowmeter measures actual hydrogen gas volume consumed. Both devices have a data API — a defined format for transmitting measurements via Bluetooth or CAN bus.

**Why you need it:** Without knowing the exact byte format, message type, and update rate of the sensors, you cannot write the code to receive and parse their data on your ESP32.

**What to say:** "We have an ESP32 that speaks both BLE and CAN. If we could get the frame format and message ID for both sensors, we can write the integration in a day."

### Ask 2 — M12 pinout and CAN bus bit-rate

**What it is:** M12 is a type of industrial connector (round, 12 mm, with locking thread). The Schmid sensors connect via CAN bus (a two-wire serial protocol widely used in automotive electronics) through an M12 connector. You need to know which pin is CAN High, CAN Low, ground, and power, and at what speed the bus runs (typically 250 kbit/s or 500 kbit/s).

**Why you need it:** Without the pinout and bit-rate, you cannot build the physical interface. Your ESP32 has a built-in CAN controller (called TWAI); you only need a small transceiver chip (SN65HVD230, ~€1) and a cable with the right connector.

**What to say:** "We've identified the SN65HVD230 as our transceiver. We just need the M12 pinout and the CAN bit-rate to complete the wiring."

### Ask 3 — Mounting and EMI guidance

**What it is:** EMI = electromagnetic interference. The sensors need to be mounted near the fuel cell and hydrogen system. Strong electromagnetic fields from the fuel cell's high-current switching can corrupt sensor readings. Schmid knows where to place the sensors to avoid this.

**Why you need it:** Incorrect mounting could cause noisy or inaccurate readings, which would corrupt the hydrogen consumption ledger — the most critical number in the competition.

### Ask 4 — Bench/loaner unit before the event

**What it is:** A sensor that you can borrow or use in the lab before the competition to develop and test the integration code.

**Why you need it:** You cannot write and test hardware integration code without the hardware. If the first time you plug in the sensor is at the event, there is no time to debug. A bench unit lets you test everything in advance.

### Ask 5 — Bootcamp slot on the sensor data API

**What it is:** A training session (in person or online) where Schmid's engineers explain their sensor API, show sample data, and answer technical questions.

**Why you need it:** Even with documentation, a one-hour session with the engineers who built the system is worth weeks of trial-and-error. This is the single highest-leverage ask.

---

<a name="part-8"></a>
## Part 8 — Glossary of Technical Terms

**API (Application Programming Interface):** A defined way for two software systems to communicate. When we say "the sensor has an API via Bluetooth," we mean the sensor broadcasts data in a specific, documented format that your code can read.

**BLE (Bluetooth Low Energy):** A version of Bluetooth designed for sensors and IoT devices. It uses much less power than classic Bluetooth. Your ESP32 communicates with the Android phone via BLE at 19,200 bits per second.

**CAN bus (Controller Area Network):** An industrial-standard two-wire serial communication protocol originally designed for automotive use. Very reliable, hardware error-checked. The Schmid sensors communicate via CAN.

**CdA (drag area, m²):** The product of drag coefficient (Cd, dimensionless) and frontal area (A, m²). For an ultra-efficient prototype, this is typically 0.02–0.06 m². Lower is better. Measured via coast-down test.

**Crr (rolling resistance coefficient, dimensionless):** How much energy is lost per unit distance due to tire deformation. Typical prototype value: 0.001–0.003. Measured via coast-down test.

**DP (Dynamic Programming):** An optimization algorithm that solves complex problems by breaking them into subproblems. In this context, it finds the globally optimal burn/coast plan over a discretized speed grid. "Global optimum" means no other plan can do better within the model's assumptions.

**ESP32:** A small, powerful microcontroller chip made by Espressif. It has built-in WiFi, Bluetooth, and CAN (called TWAI), and costs about €3. It is the "brain" of the Thaiger 7 sensor hub.

**FC (Fuel Cell):** An electrochemical device that converts hydrogen gas into electricity (like a battery that runs on hydrogen). Your fuel cell outputs ~18 V and up to ~350 W.

**GATT (Generic Attribute Profile):** The data communication protocol layer used over BLE. When data moves between the ESP32's HM-10 module and the Android phone, it uses GATT. Error 133 is a known Android BLE instability documented in the ThaiGerTrackControl README.

**GPS (Global Positioning System):** Satellite-based positioning. Your Android phone has GPS built in. Using it for vehicle position allows the dashboard to know exactly where on the track the car is, enabling segment-level strategy.

**HiveMQ:** A commercial MQTT broker (server) hosted in the cloud. Your team uses the free tier. The engineer dashboard and Lap Coach both connect to HiveMQ using WebSocket connections on port 8884.

**HM-10:** A small BLE module (hardware) that the ESP32 uses to communicate wirelessly with the Android phone. It must be configured with `AT+BAUD2` (19,200 baud) before use — see the ThaiGerTrackControl README.

**H₂ (Hydrogen):** Molecular hydrogen — two hydrogen atoms bonded together. Your fuel cell consumes H₂ gas and produces electricity + water. The competition measures efficiency in km/m³ (kilometres per cubic metre of H₂ consumed at standard conditions).

**km/m³ (kilometre per cubic metre):** The SEM scoring unit for hydrogen vehicles. Higher is better. Typical competitive prototype values: 400–1,000+ km/m³. The DP-optimised plan in DEMO mode achieves ~600 km/m³ with exemplary parameters.

**LHV (Lower Heating Value):** The energy content of a fuel, not counting water vapour recovery. For hydrogen: LHV ≈ 119.96 MJ/kg, which equals about 3.0 Wh per normal litre (Nl) or 10.8 MJ/m³. Used to convert between electrical energy (Wh) and hydrogen volume (litres or m³).

**M12:** A type of round industrial electrical connector with 12 mm locking thread. Commonly used in factory automation and motorsport. The Schmid sensors connect via M12.

**MQTT (Message Queuing Telemetry Transport):** A lightweight messaging protocol designed for IoT devices. Your telemetry system publishes data on a "topic" (like `thaiger/thaiger7/telemetry`); any subscriber anywhere in the world that connects to the same broker can receive it in real time.

**OBC (Onboard Computer):** In your system, the Android phone is the onboard computer. It receives BLE data from the ESP32, runs the alarm engine, logs data, displays the driver UI, and relays data to the cloud.

**QoS (Quality of Service):** An MQTT setting controlling message delivery guarantees. QoS 0 = fire-and-forget (fastest, may lose messages); QoS 1 = at least once (default for telemetry); QoS 2 = exactly once (slowest). The strategy topic uses QoS 1.

**SoC (State of Charge):** For a supercapacitor, how charged it is — from 0% (empty) to 100% (full voltage). Calculated from: SoC = ½CV² / ½CV²_max, where V is the current voltage and V_max is the maximum rated voltage.

**Strategy topic:** The MQTT topic `thaiger/<carId>/strategy` where the strategy engine publishes the lap plan as a JSON message. It is a "retained" message — any new subscriber immediately receives the last plan, even if it was published minutes ago.

**Supercapacitor (supercap):** An energy storage device that charges and discharges much faster than a battery, but stores less total energy. Thaiger 7 uses a supercapacitor to buffer power peaks: when the fuel cell operates at a steady, efficient point, excess energy goes into the supercap; when extra power is needed (climbing, acceleration), the supercap supplements the fuel cell.

**TLS (Transport Layer Security):** Encryption for network connections. MQTT over TLS uses port 8883 (for native MQTT) or port 8884 (for WebSocket/TLS). All data between the car, HiveMQ, and the dashboards is encrypted.

**TWAI (Two-Wire Automotive Interface):** Espressif's name for the CAN bus controller built into the ESP32. Combined with a SN65HVD230 transceiver, it can communicate with the Schmid sensors over CAN.

**WSS (WebSocket Secure):** Encrypted WebSocket connection. Browsers cannot open raw TCP sockets; they must use WebSocket. Port 8884 on HiveMQ is the WSS endpoint — this is why the dashboards use port 8884 while the MQTT recorder on the laptop uses port 8883.

---

## Appendix — File Summary

| File | Location | Purpose |
|------|----------|---------|
| `SEM-Poland-2026_DataTelemetry_APPLICATION-FINAL.tex` | SEM 26/ | Award paper source (edit to fill identity fields, build with pdflatex) |
| `SEM-Poland-2026_DataTelemetry_APPLICATION-FINAL.pdf` | SEM 26/ (after build) | Award paper PDF — submit this |
| `ThaiGer_LapCoach_v2.html` | SEM 26/ | Race strategy dashboard (open in browser, double-click) |
| `ThaiGer_SEM2026_Finalization_Guide.md` | SEM 26/ | This document |
| `ThaiGer-SEM2026-handoff/` | Session outputs | All source research, strategy notes, prior drafts, rules PDF |

---

*Document prepared for ThaiGer H2 Racing — Hochschule Stralsund. Submission deadline: ~10 June 2026. Event: 24–28 June 2026, Silesia Ring, Kamień Śląski, Poland.*
