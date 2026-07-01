# AdaptiFit — Unified Inclusive Health & Fitness Project

> Your pace. Your ability. Your movement — for body **and** mind.
<img width="1872" height="1018" alt="image" src="https://github.com/user-attachments/assets/e647133f-5533-442b-96bf-77a84c039469" />


**Run the whole thing from the repo root:**

```powershell
./start.ps1     # installs deps (first run), prepares the DB, starts on http://localhost:3000
./stop.ps1      # stops it
```

What was merged into AdaptiFit:

- **gym-buddy / AccessFit → "Live Coach"** — real on-device MediaPipe rep
  counting and live form coaching.
- **MindGym → "Mind Gym"** — cognitive training (focus timer, attention game,
  memory match, daily check-in) for ADHD, brain fog and memory.
- **Adaptive Motion Gym (this folder's original `src/`)** — the adaptive,
  accessibility-first, body-neutral philosophy (Body Scan, Exercises, Profile).
- Everything else AdaptiFit already provides: Dashboard, Breathing, Mood,
  Nutrition, Community, Wearable, Crisis support, voice navigation, TTS and a
  global accessibility panel.

See **[`hi/README.md`](./hi/README.md)** for the full feature map and details.

The standalone prototypes (`MindGym/`, `gym-buddy/`, and the original
Adaptive Motion Gym in the root `src/`) are kept below and in their folders for
reference only.

---

<details>
<summary><strong>Reference: the original Adaptive Motion Gym module (now part of AdaptiFit)</strong></summary>

# Adaptive Motion Gym

> Your pace. Your ability. Your movement.

An inclusive, accessibility-first AI movement companion for people who are often
excluded by traditional fitness apps. Adaptive Motion Gym builds personalized,
safety-aware movement routines around how your body actually moves today — not
around a one-size-fits-all idea of "standard" fitness.

This is the **physical fitness / adaptive workout module** of a larger inclusivity
and wellness project (which may also include a Mental Gym, accessibility tools and
community features).

---

## Problem statement

Most fitness apps assume every user can stand, jump, balance, use both arms and
both legs, get onto the floor, and follow visual-only videos. That excludes a huge
number of people. Adaptive Motion Gym does the opposite: it adapts the workout to
the person, with dignity, safety and control built in from the start.

> Fitness should adapt to the person, not force the person to adapt to standard fitness.

---

## Target users

- Wheelchair users and people who move primarily seated
- People with one arm / limited arm use, limb differences, or prosthetics
- People with one leg / limited leg use
- People with balance challenges
- People with knee, shoulder, back, hip, or other areas to protect
- People recovering from injury, including veterans with physical limitations
- People across all body sizes and heights
- People with low fitness confidence
- Anyone who needs seated, supported, low-impact, or adapted movement
- Anyone who needs screen-reader, keyboard, high-contrast, large-text, voice, or
  reduced-motion support

---

## Key features implemented

- **Ability Profile** — functional, body-neutral intake (never a "what's wrong" form),
  stored locally, fully editable and resettable.
- **Adaptive Intake Form** — Quick Start and Detailed modes, grouped into friendly
  sections with progressive disclosure.
- **Support Mode** — the routine adapts to chairs, walls, wheelchairs, bands, etc.
- **Adaptive Workout Generator** — 8–10 personalized exercises by default, each with
  instructions, reps, rest, safety notes, easier/harder options, a seated alternative,
  voice-ready text, a visual description and a confidence note.
- **Smart Exclusion Engine** — a deterministic safety layer that filters out anything
  conflicting with the user's mobility, support, pain areas, equipment or preferences.
- **Safety Validation Loop** — every routine is validated before it is shown; nothing
  unsafe reaches the screen.
- **Exercise Replacement** — "This does not work for me" swaps in a safe alternative
  that respects the same constraints and never repeats a rejected option.
- **Adaptive Regeneration** — reshape the whole routine any time (easier, seated,
  low-impact, chair-only, more core, etc.) without losing your place.
- **Guided Session Mode** — a **get-ready 3-2-1 countdown** before each exercise, an
  **animated movement demonstration**, a **circular rest-timer ring**, a **total
  elapsed timer**, a **per-exercise progress bar**, optional **sound cues**, plus
  start/pause/resume/skip/replace, progress dots, next-up preview, keyboard usable.
- **Movement twin & GIF** — an optional, consent-based **photo upload or camera body scan**
  (or manual sliders) sizes a rough, stylised **“movement twin”** to your approximate
  height/build at onboarding; it is **saved and updatable any time** from the Profile screen,
  animates each movement during the session, and you can **generate and download a real
  animated GIF** of any move. Stylised — never a photoreal or medical body model; no images stored.
- **Workout reminders** — an optional daily reminder with a time picker and browser
  notifications (fires while the app is open), plus a gentle in-app nudge when it is due.
- **AI movement visuals** — optionally generate an AI illustration of the current move,
  adapted to your profile (wheelchair / seated / one-arm), via a **free, keyless** provider
  (Pollinations.ai). On-demand, with a graceful fallback to the stylised twin; only a text
  prompt is sent — **never your photo** — and it is clearly labelled AI-generated, not photoreal.
- **Voice-Guided Mode** — browser text-to-speech with a graceful captions fallback.
- **Motion Check (optional)** — consent-based camera feedback that is gentle and
  explicitly non-medical, never stores frames, and is fully optional.
- **Adaptive Motion Sketch** — a rough, **animated**, posture-aware SVG guide (seated /
  wheelchair / supported / standing) whose limbs demonstrate the movement per exercise,
  with text alternatives — explicitly not a medical body model, and frozen to a neutral
  pose under reduced motion.
- **Global Accessibility Panel** — light/dark theme, colour-vision palettes, high
  contrast, large text, reduced motion, dyslexia-friendly font, simple language, voice
  guidance, captions, and sound cues.
- **Inclusive Coaching Tone** — gentle, calm, energetic, motivational, minimal, simple,
  or trauma-aware — never shaming.
- **Post-Workout Feedback** — collected once after the workout and stored for next time.
- **Benefit Summary** — Confidence Points, movement minutes, exercises completed,
  muscles trained, adaptations used, comfort/confidence, streak — never fake medical
  percentages or weight-loss framing.
- **Inclusive Badges** — celebrate effort, adaptation and consistency.
- **Safety Labels** — every card shows why an exercise is suitable.
- **Mental Gym Bridge** — a lightweight breathing cooldown / reflection prompt.
- **Share / Export** — copy a plain-text summary for a caregiver, trainer or teammate.

---

## Accessibility features implemented

- Keyboard-operable core flow with a "skip to main content" link
- Visible focus states everywhere (`:focus-visible`)
- Semantic landmarks, `role="switch"`/`radiogroup`, `aria-pressed`, `aria-live` regions
- High contrast mode, large text mode, reduced motion mode (also respects
  `prefers-reduced-motion`), dyslexia-friendly font, simple-language mode
- Light & dark themes (follow the system preference by default) with a one-tap header toggle
- Colour-vision palettes (deuteranopia, protanopia, tritanopia) for colour blindness,
  layered on top of the "never colour alone" rule
- Voice guidance with captions/text-instruction fallback, plus optional sound cues
- Text alternatives for every visual movement guide
- No information conveyed by colour alone (labels + icons accompany colour)
- Accessible names on all buttons and form inputs; clear, respectful error/empty states
- Responsive, mobile-first layout

---

## Inclusivity principles followed

- Body-neutral, disability-respectful, trauma-aware language throughout
- Functional questions ("how does your body move today?") instead of diagnosis labels
- Progress is measured by movement and confidence — never appearance, weight or shame
- Support, seated and one-arm-friendly options are first-class, not afterthoughts
- The user is always in control: replace, reshape, pause or stop anything, any time

---

## Safety & medical disclaimer

Adaptive Motion Gym provides **general inclusive movement suggestions only**. It does
**not** diagnose, treat, cure, medically prescribe, or replace professional care, and it
does **not** guarantee that any exercise is safe for you. Stop if you feel pain,
dizziness, numbness, or discomfort, and consult a qualified professional for medical
conditions, injuries or rehabilitation needs.

---

## AI / LLM usage explanation

This module runs **fully client-side with a deterministic engine** as its primary mode,
so it works with **no API key, no backend and offline** — ideal for a reliable demo.

- **Safety is never delegated to an LLM.** The Smart Exclusion Engine and Safety
  Validation Loop are deterministic (see `src/engine/`). They build constraints from the
  Ability Profile and validate every exercise against them.

### Optional AI Coach (GitHub Copilot CLI)

There is an **optional** "AI Coach" feature that generates a short, supplementary,
non-medical encouragement note for a routine. It is powered by the **GitHub Copilot CLI**
via a tiny local server (`server/ai-coach.mjs`), because a browser cannot invoke a CLI
directly.

- Run it with `npm run ai-server` (needs the `copilot` CLI installed and authenticated).
- The browser calls `http://localhost:8787/api/ai-coach`; if the server is not running,
  the card shows a friendly "offline" message and **the app keeps working fully**.
- **Cost note:** every AI Coach request consumes **GitHub Copilot AI Credits**, so it is
  always an explicit, opt-in user action — never automatic.
- **Security:** the server binds to `127.0.0.1` only and passes the prompt to the CLI via
  an environment variable (never interpolated into a shell string), so command injection
  is not possible. The model is used only for encouraging text — never for safety
  decisions, which stay in the deterministic engine.
- **Swappable:** point `VITE_AI_COACH_URL` at any compatible endpoint (e.g. a hosted API)
  if you prefer a different provider. The contract for AI-assisted *exercise* generation
  (not yet enabled) is: the model may suggest, but output must be parsed into the
  `Exercise` shape and **re-validated by `src/engine/safetyEngine.ts`** before display.

---

## Demo / fallback mode

The module is designed to never look broken:

- Works without any LLM/API key (deterministic generation is the default).
- Works without camera permission (Motion Check is optional and degrades gracefully).
- Works without speech synthesis (captions/text instructions are always available).
- Works if image upload is skipped (profile answers are used instead).
- Works without a stored profile (Quick Start and demo personas seed one instantly).
- Includes a local inclusive exercise library and three ready-made demo personas.

---

## How to run

```bash
npm install
npm run dev      # start the dev server (http://localhost:5173)
```

Other scripts:

```bash
npm run build      # type-check (tsc --noEmit) and build for production
npm run preview    # preview the production build
npm run ai-server  # OPTIONAL: start the Copilot-CLI-backed AI Coach server (uses AI credits)
npm test           # run the safety-engine unit tests (Vitest)
npm run typecheck  # type-check only
```

Requirements: Node 18+ (built and tested on Node 24). Modern browser. For Motion Check
and the microphone-free camera preview, the browser needs camera permission; on most
browsers camera APIs require `localhost` or HTTPS.

---

## Environment variables needed

**None required.** The app runs entirely client-side with no secrets, keys, or backend.

Optional:

- `VITE_AI_COACH_URL` — override the AI Coach endpoint (default
  `http://localhost:8787/api/ai-coach`). Point it at any compatible provider if you do
  not want to use the local Copilot CLI server.
- `VITE_IMAGE_GEN_URL` — override the AI movement-image provider base (default: the free,
  keyless `https://image.pollinations.ai/prompt/`). Swap in another text-to-image base or a
  hosted/Azure OpenAI image endpoint if you prefer.
- `AMG_AI_PORT` / `AMG_AI_SHELL` — override the AI Coach server port / shell.

Keep any keys out of source control (use `.env.local`, which is already git-ignored).

---

## Demo personas

Three personas are included (see `src/data/demoPersonas.ts`) and surfaced as one-click
buttons on the landing screen:

1. **Wheelchair Upper-Body Strength** — seated only, no floor, resistance band, upper
   body + core. Avoids squats, lunges, running, jumping, planks, burpees, floor push-ups.
2. **One-Arm Beginner / Veteran** — one available arm, standing, chair + wall + band, no
   floor. Avoids standard push-ups, pull-ups, two-arm planks, two-handed loaded moves.
3. **Knee-Friendly Low Impact** — standing with knee sensitivity, chair + band, low
   impact. Avoids jumping, lunges, deep squats, running.

---

## Demo script

1. Open Adaptive Motion Gym.
2. Select **"Try Wheelchair Strength Demo."**
3. The app generates an adaptive routine — notice every exercise is seated /
   wheelchair-friendly, with "Seated only · No floor · Balance-supported · Low impact"
   adaptation labels.
4. On any exercise, click **"This does not work for me"** and pick a reason
   (e.g. *I do not have the equipment*).
5. Watch the app swap in a safe alternative that still respects every constraint.
6. Click **"Start guided workout."**
7. Open the **Accessibility** panel and try **Dark theme**, a **Colour-vision** palette,
   **Voice guidance**, **High contrast** or **Large text** — all apply instantly app-wide.
8. Use **Pause / Done / Skip / Replace**, then **Finish workout**.
9. Submit the post-workout feedback.
10. View your **Confidence Points**, badges, muscles trained, adaptations used and
    summary — then **Copy summary** to share.
11. (Optional) Run `npm run ai-server` and click **"Ask the AI coach"** on the plan for a
    Copilot-CLI-generated encouragement note.

---

## Folder / file structure

```
.
├─ index.html
├─ package.json
├─ tsconfig.json
├─ vite.config.ts
├─ adaptive-motion-gym-brief/      # reference docs (brief, specs, data, guidelines)
├─ server/
│  └─ ai-coach.mjs                 # optional Copilot-CLI-backed AI Coach server
└─ src/
   ├─ main.tsx                     # entry; wraps app in providers
   ├─ App.tsx                      # screen routing + flow orchestration
   ├─ index.css                    # design system + accessibility theming (data-attrs)
   ├─ types/                       # shared TypeScript types
   ├─ data/                        # exercise library, options, badges, personas, defaults
   ├─ engine/                      # constraints, safety engine, generator, coaching (+ tests)
   ├─ context/                     # ProfileContext, AccessibilityContext
   ├─ hooks/                       # useSpeech, useMotionCheck, useAiCoach
   ├─ components/                  # Inputs, MotionSketch, ExerciseCard, AccessibilityPanel…
   └─ screens/                     # Landing, Intake, Plan, Session, Feedback, Summary, Profile
```

---

## Testing notes

- `src/engine/safetyEngine.test.ts` contains 13 deterministic tests covering:
  - every demo persona produces a fully validated routine,
  - seated-only/wheelchair users get no standing or floor exercises,
  - one-arm users get no two-arm-required exercises (no push-ups, planks, wall push),
  - knee-pain users get no jumping/lunges/deep squats/knee-loading moves,
  - low-balance users get no unsupported single-leg or fast-direction moves,
  - replacement respects constraints, never duplicates, never repeats a rejected option,
  - "seated" regeneration yields a seated-only routine; "shorter" reduces the count,
  - single-exercise evaluation blocks/allows correctly (e.g. band moves need a band).
- Run with `npm test`. The flow has also been manually smoke-tested end to end.

Suggested manual checks: keyboard-only navigation, high-contrast/large-text toggles,
reduced motion, voice on/off, camera denied, image skipped, and each demo persona.

---

## Known limitations

- Generation is rule-based (no LLM wired in by default); variety is bounded by the local
  exercise library. This is a deliberate trade-off for offline reliability and safety.
- Motion Check uses simple brightness/frame-difference heuristics for gentle, non-medical
  feedback — it is not pose estimation and makes no correctness claims.
- The **body scan** is an approximate silhouette estimate (foreground vs background), not
  true body measurement or pose estimation; the avatar is a **stylised stick figure**, not
  a photoreal render of you. Photoreal AI image generation of a user's body is intentionally
  not done (no image-generation tool, and it would conflict with the body-neutral / privacy
  guardrails). Movement GIFs are rendered from the stylised avatar via the `gifenc` encoder.
- Persistence is `localStorage` (per device/browser), appropriate for a demo.
- Voice quality depends on the browser's available speech voices.
- `npm audit` reports dev-only advisories in the Vite/esbuild toolchain; **production
  dependencies report 0 vulnerabilities** (`npm audit --omit=dev`).

---

## Future improvements

- Optional LLM-assisted generation with the same deterministic re-validation gate.
- Real pose estimation for Motion Check (still optional and non-diagnostic).
- A larger exercise library and richer Adaptive Motion Sketches.
- Cloud sync with consent, and deeper Mental Gym integration.

---

## Privacy notes

- Your Ability Profile is stored **only on this device** (`localStorage`) to personalize
  movement suggestions. You can update or reset/delete it any time from the Profile screen.
- Image upload and camera-based Motion Check are **optional and consent-based**. You can
  skip them and use the whole app.
- **No camera frames, images, or videos are ever stored.** Motion Check keeps only a tiny,
  in-memory, downscaled buffer to compare against the next frame, which is then overwritten.
  The optional body scan likewise stores **no image** — only two numbers (approximate height
  and build scale factors) for sizing the stylised avatar.
- **AI movement visuals** send only a short **text prompt** (the movement + your support needs,
  e.g. “a person using a wheelchair”) to a free third-party image service (Pollinations.ai).
  Your photo is **never** sent. The feature is opt-in/on-demand and falls back to the stylised
  twin when offline.
- We collect only what is needed for personalization and prefer functional questions over
  diagnosis labels.

</details>
