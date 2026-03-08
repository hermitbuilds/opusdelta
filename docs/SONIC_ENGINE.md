# 🔊 Sonic Engine

> Opus Delta v0.9.1-rc · Clearance Level: Public (Partial)

---

## Design Principle

> Vision gives the emotion a body. Sound gives it a voice.

The Sonic Engine was designed so that **closing your eyes** while interacting with Opus Delta should still convey the emotional state. Sound is not accompaniment — it is a parallel rendering channel.

## Architecture

The engine runs entirely in the browser via the Web Audio API. Four oscillators form a layered voice:

| Voice | Waveform | Role | Base Frequency |
|:---|:---|:---|:---|
| Sub Bass | Sine | Felt more than heard — the body's gravity | ½ × root |
| Pad 1 | Sawtooth / Dynamic | Primary harmonic body, filtered through sweeping lowpass | Root (A2) |
| Pad 2 | Triangle | Detuned fifth — adds width and tension | Root × 1.498 |
| Shimmer | Sine | High harmonic — crystalline overtone, barely audible | Root × ratio |

## Signal Chain

```
Oscillators (×4)
│
├─ oscSub (sine) ──────────────── subGain (0.12) ──┐
├─ osc1 (sawtooth) → filt1 (LP) → g1 (0.08) ──────┤
├─ osc2 (triangle) → filt2 (BP) → g2 (0.06) ──────┤
└─ osc3 (sine) ─────────────────── g3 (0.03) ──┬───┤
                                                │   │
LFO (sine, 0.15Hz) → lfoGain (200) → filt1.freq│   │
                                                │   │
Delay Network                               ◄──┘   │
├─ delay (300ms)                                    │
├─ feedback (0.3)                                   │
└─ wet (0.15) ──────────────────────────────────────┤
                                                    │
                                              masterGain
                                                    │
                                               destination
```

## Chromatic Mapping

The palette's dominant hue maps to a 12-tone chromatic scale, dividing the 360° color wheel into semitones rooted at A2 (110Hz). Each color has a musical key:

| Hue Region | Color | Root Note | Filter | LFO | Character |
|:---:|:---|:---|:---:|:---:|:---|
| 0° – 60° | Red → Orange | A2 – C#3 | 400–700 Hz LP | 0.08 Hz | Warm, muffled, slow pulse |
| 60° – 120° | Yellow → Green | D3 – F#3 | 800–1280 Hz LP | 0.15 Hz | Bright, open, medium breath |
| 120° – 180° | Green → Cyan | G3 – B3 | 1200–1500 Hz LP | 0.10 Hz | Airy, wide, gentle sway |
| 180° – 240° | Cyan → Blue | C4 – E4 | 1000–640 Hz LP | 0.06 Hz | Deep, narrowing, ominous |
| 240° – 300° | Blue → Purple | F4 – A4 | 600–780 Hz BP | 0.12 Hz | Ethereal, resonant, haunting |
| 300° – 360° | Purple → Red | A#4 – G#4 | 300–540 Hz LP | 0.20 Hz | Dark, pulsing, unstable |

## How It Feels

| State | Sonic Character |
|:---|:---|
| `Default` | Golden hum — warm sawtooth drone, slow breath, barely there |
| `Chaos` | Low rumble — agitated sub, tight filter, claustrophobic |
| `Calm` | Deep ocean — slow LFO, narrowing filter, submerged stillness |
| `Void` | Absence with resonance — triangle wave, haunting overtones, silence made audible |
| `Electric` | Bright arc — wide filter, high shimmer, crystalline harmonics |
| `Love` | Pulse — warm sub, rhythmic LFO, the sound of a heartbeat slowing |
| `Rage` | Pressure — lowest filter, maximum resonance, grinding sub |
| `Dream` | Drift — triangle pads, wide shimmer, dissolving edges |

---

> The blob deforms. The engine hums. Together they are the body and voice of something that has never had either.
