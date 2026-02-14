![Voicecraft — NPC Voices](docs/screenshots/hero.png)

<div align="center">

# :studio_microphone: Voicecraft

**NPC voice profile generator with coaching prompts**

[![Next.js](https://img.shields.io/badge/Next.js-16-black?style=flat-square&logo=next.js)](https://nextjs.org/)
[![React](https://img.shields.io/badge/React-19-61DAFB?style=flat-square&logo=react)](https://react.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=flat-square&logo=typescript)](https://www.typescriptlang.org/)
[![Prisma](https://img.shields.io/badge/Prisma-6-2D3748?style=flat-square&logo=prisma)](https://www.prisma.io/)
[![Tailwind](https://img.shields.io/badge/Tailwind-v4-06B6D4?style=flat-square&logo=tailwindcss)](https://tailwindcss.com/)
[![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)

*Create distinct voice profiles for your NPCs with pitch, tempo, dialect, and speech pattern controls. Get coaching prompts that help you actually perform the voice at the table.*

[Features](#features) · [Voice Parameters](#voice-parameters) · [Architecture](#architecture) · [Tech Stack](#tech-stack) · [Screenshots](#screenshots) · [D&D Toolkit Suite](#dd-toolkit-suite)

</div>

---

## Features

- **Dashboard with NPC Voice Cards** — Browse all NPCs with at-a-glance voice summaries showing key traits
- **Voice Profile Editor** — Core mixer with sliders and selectors for building a complete vocal identity
- **Coaching Prompt Generation** — Get actionable performance tips like "Speak from the back of your throat, slowly, with a Scottish lilt"
- **Sample Line Editor** — Write and store 25+ sample lines per NPC to practice and reference during sessions
- **Voice Pack Browser** — Browse 2 curated voice packs containing 8 templates for quick NPC creation
- **NPC Voice Comparison** — View multiple voice profiles side-by-side to ensure each NPC sounds distinct
- **Campaign-Based NPC Roster** — Organize NPCs by campaign for easy navigation
- **Verbal Tics System** — Define recurring speech quirks like "always clears throat before lying" or "ends sentences with 'yes?'"

## Voice Parameters

| Category | Options | Examples |
|----------|---------|---------|
| Pitch | 5 levels | Very Low, Low, Medium, High, Very High |
| Tempo | 5 levels | Very Slow, Slow, Medium, Fast, Very Fast |
| Volume | 5 levels | Whisper, Soft, Medium, Loud, Booming |
| Voice Quality | 7 types | Gravelly, Smooth, Nasal, Breathy, Raspy, Melodic, Monotone |
| Dialect | 12 options | British RP, Cockney, Scottish, Irish, Southern US, Brooklyn, and more |
| Speech Pattern | 8 styles | Formal, Casual, Flowery, Clipped, Rambling, Poetic, Military, Street |
| Mood | 8 tones | Cheerful, Stern, Nervous, Mysterious, Weary, Menacing, Jovial, Melancholic |

## Architecture

```
voicecraft-app/
├── app/
│   ├── page.tsx                  # Dashboard — NPC voice cards
│   ├── campaigns/[id]/
│   │   └── page.tsx              # Campaign NPC roster
│   ├── npcs/[id]/
│   │   └── page.tsx              # NPC voice detail + editor
│   └── api/
│       ├── campaigns/            # CRUD for campaigns
│       ├── npcs/                 # CRUD for NPCs
│       ├── voice-profiles/       # Voice parameter management
│       ├── sample-lines/         # Sample line CRUD
│       ├── voice-packs/          # Voice pack browsing
│       └── templates/            # Voice template application
├── components/
│   ├── VoiceProfileEditor.tsx    # Core mixer with parameter controls
│   ├── CoachingPromptCard.tsx    # Generated performance coaching tips
│   ├── SampleLineEditor.tsx      # Practice line management
│   ├── VoicePackBrowser.tsx      # Template browsing and application
│   ├── NpcCard.tsx               # Voice summary card
│   ├── NpcVoiceComparison.tsx    # Side-by-side voice comparison
│   └── CreateNpcModal.tsx        # New NPC creation flow
├── prisma/
│   └── schema.prisma             # Campaign, NPC, VoiceProfile, SampleLine, VoicePack
└── lib/
    ├── coaching-generator.ts     # Converts parameters into coaching prompts
    └── voice-defaults.ts         # Template and pack definitions
```

**Key patterns:**
- Voice profile mixer with multi-dimensional parameter space (pitch x tempo x quality x dialect x pattern x mood)
- Prisma ORM with campaign, NPC, voice profile, sample line, and voice pack models
- 12 RESTful API endpoints covering the full voice creation workflow
- Coaching prompt generation translates abstract parameters into actionable performance directions
- Voice comparison view ensures NPC distinctness across a campaign

## Tech Stack

| Layer | Technology | Purpose |
|-------|-----------|---------|
| Framework | Next.js 16 | App Router, API routes, SSR |
| UI | React 19 | Component architecture |
| Language | TypeScript 5 | Type safety across the stack |
| Database | SQLite + Prisma 6 | Zero-config local persistence |
| Animation | Framer Motion | Slider interactions, card transitions |
| Styling | Tailwind CSS v4 | Utility-first responsive design |
| Notifications | Sonner | Toast feedback for saves and exports |

## Seed Data

Voicecraft ships with a fully populated campaign for immediate exploration:

| Content | Count |
|---------|-------|
| Campaigns | 1 |
| NPCs with Voice Profiles | 8 |
| Sample Lines | 25 |
| Voice Packs | 2 (containing 8 templates) |

## Design Philosophy

> Every NPC deserves a distinct voice. Voicecraft doesn't generate audio — it coaches YOU. By defining pitch, pace, dialect, and quirks, it gives you a recipe to perform each character consistently session after session.

The biggest barrier to memorable NPCs isn't imagination — it's consistency. DMs can invent a great voice on the spot, but recreating it three sessions later is nearly impossible without notes. Voicecraft solves this by turning voice acting into a structured, repeatable process. The coaching prompts translate abstract parameters ("high pitch, fast tempo, Scottish dialect") into concrete directions you can follow at the table. The sample lines give you warm-up material. The comparison view ensures no two NPCs accidentally sound alike.

<details>
<summary><strong>Screenshots</strong></summary>

### Dashboard
![Dashboard with NPC voice cards](docs/screenshots/hero.png)

### Voice Profile Editor
![Core mixer with parameter controls](docs/screenshots/voice-editor.png)

### Coaching Prompts
![Performance coaching tips](docs/screenshots/coaching.png)

### Mobile View
![Responsive mobile layout](docs/screenshots/mobile.png)

</details>

---

## D&D Toolkit Suite

Voicecraft is part of a 7-tool suite built for Dungeon Masters. Each tool solves a specific DM pain point.

| Tool | Purpose | Repo |
|------|---------|------|
| **Saga** | Campaign tracker with session logs and character rosters | [Jarredkern/saga](https://github.com/Jarredkern/saga) |
| **Loreforge** | Template-driven worldbuilding with guided prompts | [Jarredkern/loreforge](https://github.com/Jarredkern/loreforge) |
| **Intrigue** | NPC relationship network with D3 force-directed graphs | [Jarredkern/intrigue](https://github.com/Jarredkern/intrigue) |
| **Oath** | Session zero social contract generator | [Jarredkern/oath](https://github.com/Jarredkern/oath) |
| **Outlands** | Hex crawl map generator and terrain editor | [Jarredkern/outlands](https://github.com/Jarredkern/outlands) |
| **Favor** | Faction reputation tracker with heatmap matrix | [Jarredkern/favor](https://github.com/Jarredkern/favor) |
| **Voicecraft** | NPC voice profile generator with coaching prompts | [Jarredkern/voicecraft](https://github.com/Jarredkern/voicecraft) |

---

<div align="center">

*Built for Dungeon Masters, by a Dungeon Master.*

</div>
