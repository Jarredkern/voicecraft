<img src="docs/screenshots/hero.png" width="100%" alt="Voicecraft" />

<div align="center">

# Voicecraft

**NPC voice builder for tabletop performers**

</div>

---

I gave an NPC a Scottish accent in session one. By session three, he was inexplicably French. Nobody corrected me. That's the problem — keeping NPC voices consistent across a campaign is nearly impossible when you're running a dozen characters off memory alone.

Voicecraft lets you build a voice profile for every NPC, then gives you coaching prompts so you can actually reproduce it at the table. I haven't seen another tool that does this.

---

## What It Does

- **Voice profile mixer** — Adjust pitch, tempo, volume, and voice quality per NPC. Combine them into something distinct and repeatable
- **12 dialect options** — Cockney to Elvish, each with pronunciation guides and sample phrases. Not just labels — actual coaching
- **8 speech patterns** — Formal, archaic, clipped, flowery, mumbling, booming, whispering. Layer these with the dialect
- **Coaching prompts** — Performance tips generated from the voice config. "Speak slower, drop your pitch on emphasized words, clip your consonants"
- **Sample lines** — Editable dialogue showing how each NPC would sound in character
- **Side-by-side comparison** — View multiple profiles next to each other so your NPCs don't all end up sounding the same

---

## Screenshots

<img src="docs/screenshots/feature-1.png" width="100%" alt="Voice profile dashboard" />

*Voice profiles — every NPC with their voice parameters at a glance*

<img src="docs/screenshots/feature-2.png" width="100%" alt="NPC roster with voice summaries" />

*NPC roster with voice summaries and coaching hints*

<img src="docs/screenshots/mobile.png" width="50%" alt="Voicecraft on mobile" />

*Pull up an NPC's voice profile mid-session*

---

<details>
<summary>Technical Details</summary>

<br>

**Stack:** Next.js 16, TypeScript, React 19, Tailwind CSS, Prisma 6, SQLite

- Voice profile mixer combines 5+ independent parameters into unique coaching prompts
- Campaign, NPC, VoiceProfile, SampleLine, VoicePack, and Template models
- 12 API routes covering campaigns, NPCs, voice profiles, sample lines, and templates

</details>

---

Part of a [set of tools](https://github.com/CandyFlex) I built for tabletop GMs. This one solves a problem I haven't seen anyone else tackle.
