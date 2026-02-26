# ☁️ Vibe Weather

**Internet Mood Forecast** — A weather app, but instead of actual weather, it shows the current emotional temperature of the internet.

![Vibe Weather](https://img.shields.io/badge/vibes-check-blueviolet) ![No Backend](https://img.shields.io/badge/backend-none-green) ![License](https://img.shields.io/badge/license-MIT-blue)

## What is this?

Vibe Weather scrapes top posts from Hacker News (and Reddit when CORS allows it), runs sentiment analysis on the headlines, and presents the results as a weather forecast:

- **☀️ 28°V+** — Radiant Vibes: The internet is thriving
- **🌤️ 23-27°V** — Good Vibes: Generally positive mood
- **⛅ 18-22°V** — Mixed Signals: Some good, some bad
- **🌥️ 13-17°V** — Cloudy Mood: Leaning negative
- **🌧️ 8-12°V** — Gloomy Internet: Bad news dominates
- **⛈️ <8°V** — Internet Rage Storm: Everyone is angry

## Features

- 🔍 **Live data** from Hacker News API (+ Reddit JSON API)
- 📊 **Multi-axis sentiment analysis**: Happy↔Sad, Angry↔Peaceful, Optimistic↔Pessimistic
- 🌡️ **Temperature mapping** — sentiment score converted to an intuitive temperature scale
- 🎨 **Dynamic UI** — gradient backgrounds, glassmorphism cards, and animated particles that change based on mood
- 🌧️ **Weather particles** — rain drops when the mood is bad, floating orbs when it's good
- 📱 **Fully responsive** — works on mobile and desktop
- 🚫 **No backend needed** — pure client-side HTML/CSS/JS, runs from a single file

## How It Works

1. Fetches the top 30 stories from Hacker News and top 25 posts from Reddit
2. Runs each title through a keyword-based sentiment lexicon (AFINN-inspired)
3. Scores along three axes: happiness, peacefulness, and optimism
4. Aggregates scores into an overall "temperature" (5-35°V)
5. Renders the result with matching weather visuals

## Try It

**Live:** [keno303.github.io/vibe-weather](https://keno303.github.io/vibe-weather/)

**Local:**
```bash
# Just open the file
open index.html

# Or serve it
python3 -m http.server 8080
# → http://localhost:8080
```

## Tech Stack

- Vanilla HTML/CSS/JS (no build step, no dependencies)
- Google Fonts (Inter)
- Canvas API for particle effects
- Hacker News Firebase API
- Reddit JSON API (when CORS permits)

## Limitations

- Sentiment analysis is keyword-based, not ML — it catches obvious signals but misses sarcasm, context, and nuance
- Reddit's API often blocks cross-origin requests from browsers
- The lexicon is English-only

## Origin Story

This project was born from a voice message idea: *"What if there was a weather app, but for the internet's mood?"* — Built by an AI agent (Keno5005) based on a voice prompt from Dev Rys.

## License

MIT
