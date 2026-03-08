# ◈ Affect Mapping Reference

> Opus Delta v0.9.1-rc · Clearance Level: Public (Partial)

---

## Parameters

The Δ-Affect Engine emits six values per cycle:

```
noise ·········· 0.0 ░░░░░░░░░░░░░▓▓▓▓▓ 1.0  internal turbulence
displacement ··· 0.0 ░░░░░░░░░░░░░▓▓▓▓▓ 1.0  emotional intensity
speed ·········· 0.0 ░░░░░░░░░░░░░▓▓▓▓▓ 1.0  arousal / metabolic rate
roughness ······ 0.0 ░░░░░░░░░░░░░▓▓▓▓▓ 1.0  vulnerability ↔ guardedness
metallic ······· 0.0 ░░░░░░░░░░░░░▓▓▓▓▓ 1.0  emotional clarity
entropy ········ 0.0 ░░░░░░░░░░░░░▓▓▓▓▓ 1.0  cognitive openness
```

## Complete State Map

| Input | Noise | Disp. | Speed | Rough | Metal | Entropy | Character |
|:---|:---:|:---:|:---:|:---:|:---:|:---:|:---|
| `Default` | 0.42 | 0.28 | 0.35 | 0.30 | 0.65 | 0.50 | Gold sphere, slow breathing, latent potential |
| `Chaos` | 0.92 | 0.85 | 0.88 | 0.10 | 0.90 | 0.95 | Fractures, shatters, volatile reformation |
| `Calm` | 0.15 | 0.12 | 0.10 | 0.60 | 0.30 | 0.10 | Smooth pearl, compressed certainty, barely breathing |
| `Fire` | 0.70 | 0.65 | 0.75 | 0.05 | 0.85 | 0.78 | Combustion geometry, volatile surface |
| `Ocean` | 0.45 | 0.35 | 0.25 | 0.40 | 0.50 | 0.35 | Tidal deformation, vast rhythm |
| `Void` | 0.05 | 0.02 | 0.02 | 0.95 | 0.10 | 0.02 | Singularity, all motion stilled, dark sphere |
| `Electric` | 0.60 | 0.55 | 0.90 | 0.00 | 1.00 | 0.82 | Lightning, crystalline, every vertex a synapse |
| `Dream` | 0.50 | 0.40 | 0.15 | 0.30 | 0.60 | 0.55 | Dissolved edges, gentle drift, soft pulsing |
| `Love` | 0.35 | 0.30 | 0.20 | 0.25 | 0.55 | 0.40 | Warmth, softening, heartbeat in vertices |
| `Rage` | 0.95 | 0.90 | 0.95 | 0.02 | 0.95 | 0.98 | Critical displacement, mesh tears, computational fury |
| `Melancholy` | 0.30 | 0.20 | 0.08 | 0.70 | 0.25 | 0.20 | Weight, descending geometry, the shape of sinking |
| `Quantum` | 0.70 | 0.60 | 0.70 | 0.10 | 0.85 | 0.88 | Superposition, probability rendered as form |
| `+ 14 states` | | | | | | | `█▓▒░ restricted` |

## Sonic Mapping

Each state also maps to a unique sonic signature via chromatic color-to-frequency translation:

| State | Hue | Root Note | Filter | LFO | Sonic Character |
|:---|:---:|:---|:---:|:---:|:---|
| `Default` | 43° | A2 (110 Hz) | 615 Hz LP | 0.08 Hz | Golden hum, warm sawtooth, slow breath |
| `Chaos` | ~15° | A#2 (116 Hz) | 475 Hz LP | 0.08 Hz | Low rumble, tight filter, claustrophobic |
| `Calm` | ~200° | D4 (146 Hz) | 880 Hz LP | 0.06 Hz | Deep ocean, slow LFO, submerged stillness |
| `Void` | ~270° | F#4 (185 Hz) | 690 Hz BP | 0.12 Hz | Absence with resonance, haunting overtones |
| `Electric` | ~180° | C4 (130 Hz) | 1200 Hz LP | 0.10 Hz | Bright arc, wide filter, crystalline harmonics |
| `Love` | ~340° | G#4 (207 Hz) | 460 Hz LP | 0.20 Hz | Pulse, warm sub, rhythmic heartbeat |
| `Rage` | ~0° | A2 (110 Hz) | 400 Hz LP | 0.08 Hz | Pressure, maximum resonance, grinding |
| `Dream` | ~260° | F4 (174 Hz) | 660 Hz BP | 0.12 Hz | Drift, dissolving edges, triangle pads |
| `Quantum` | ~160° | B3 (123 Hz) | 1400 Hz LP | 0.10 Hz | Superposition, airy, unstable shimmer |

## Implementation Note

The keyword layer serves as a fallback and calibration baseline. In production, affect state is computed from model internals, not string matching. The keyword map exists primarily for the interactive demo and for ground-truth calibration of the proprietary pipeline.

---

> For full ontology access, contact **research@opusdelta.io**
