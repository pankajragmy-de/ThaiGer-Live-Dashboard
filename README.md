# ThaiGer H₂ Lap Coach

Race strategy dashboard for **Thaiger 7** — Shell Eco-marathon Poland 2026.

**[→ Open Dashboard](https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/)**

---

### What this is

A single-file, serverless race strategy tool for a hydrogen fuel cell prototype
competing at the Shell Eco-marathon Mileage Challenge (Silesia Ring, Poland,
24–28 June 2026).

- **Track:** Real Silesia Ring GPS centreline (SEM Data & Telemetry Portal)
- **Weather:** Live Open-Meteo forecast · SEM 2025 historical fallback
- **Strategy:** Dynamic-programming energy optimizer, re-planned every lap
- **Live data:** Connects to your HiveMQ MQTT broker (same credentials as `engineer_dashboard.html`)

### Files

| File | Purpose |
|---|---|
| `index.html` / `ThaiGer_LapCoach_v2.html` | The dashboard — open in any browser |
| `SEM-Poland-2026_DataTelemetry_APPLICATION-FINAL.tex` | Award paper (LaTeX source) |
| `ThaiGer_SEM2026_Finalization_Guide.md` | Step-by-step finalization guide |

### Quick start

Open `index.html` in Chrome or Firefox. DEMO mode starts automatically.

To connect live telemetry: click ⚙ → enter your HiveMQ broker credentials → switch to **LIVE MQTT**.

### Related

Telemetry system: [github.com/D0mm3c/ThaiGerTrackControl](https://github.com/D0mm3c/ThaiGerTrackControl)
