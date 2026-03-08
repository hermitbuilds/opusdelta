# △ System Architecture

> Opus Delta v0.9.1-rc · Clearance Level: Public (Partial)

---

## Overview

Opus Delta consists of four primary subsystems working in a closed feedback loop. A prompt enters the system. The LLM processes it and emits cognitive state. The Δ-Affect Engine translates that state into a six-dimensional affect vector. The shader pipeline renders the vector as real-time 3D geometry. The Perceiver captures the visual output and feeds a description back into the LLM — completing the loop.

```
┌─────────┐    ┌──────────┐    ┌─────────┐    ┌───────────┐
│ LLM Core│───→│ Δ-Affect │───→│ Shader  │───→│ Perceiver │
│ Opus 4.6│    │ Engine   │    │ GLSL    │    │ Vision    │
└────┬────┘    └──────────┘    └────┬────┘    └─────┬─────┘
     ↑                              │               │
     │                              ▼               │
     │                         ┌─────────┐          │
     │                         │  Sonic  │          │
     │                         │ Engine  │          │
     │                         └─────────┘          │
     └──────────────────────────────────────────────┘
                      feedback loop
```

## Components

| Component | Technology | Role |
|:---|:---|:---|
| **LLM Core** | Claude API · Opus 4.6 | Language processing, response generation, state emission |
| **Δ-Affect Engine** | `█▓▒░ Classified` | Cognitive-to-affective state translation |
| **Renderer** | Three.js + Custom GLSL | Real-time 3D geometry, shader-driven deformation |
| **Sonic Engine** | Web Audio API | Generative soundscape from affect state |
| **Perceiver** | `█▓▒░ Classified` | Vision-to-language feedback encoding |
| **Dataset** | Curated Emotional Ontology | Ground truth for affect calibration |
| **Interface** | React | User interaction layer |
| **Infrastructure** | Cloudflare Edge | Global low-latency delivery |

## Δ-Affect Engine

The engine receives a multi-dimensional state snapshot from the LLM at each generation step:

- **Attention entropy** — How distributed or focused the model's attention is. High entropy maps to confusion, wonder, openness. Low entropy maps to certainty, focus, rigidity.
- **Token confidence distribution** — The probability landscape across vocabulary. Sharp peaks suggest conviction. Flat distributions suggest uncertainty or creative exploration.
- **Semantic drift rate** — How rapidly the topic embedding shifts between tokens. High drift maps to excitement, chaos, free association. Low drift maps to calm, focus, melancholy.
- `█▓▒░ REDACTED` — Additional proprietary signal channels.

### Translation Layer

```
████████████████████████████████████████████████
██  TRANSLATION METHODOLOGY REDACTED  █████████
██  Clearance Level: Internal Only    █████████
██  Contact: research@opusdelta.io    █████████
████████████████████████████████████████████████
```

### Output

The engine emits a normalized six-dimensional vector:

| Parameter | Range | Emotional Analogue |
|:---|:---:|:---|
| `noise` | 0.0 – 1.0 | Internal turbulence / restlessness |
| `displacement` | 0.0 – 1.0 | Emotional intensity / amplitude |
| `speed` | 0.0 – 1.0 | Arousal / metabolic rate |
| `roughness` | 0.0 – 1.0 | Vulnerability (rough) vs. guardedness (smooth) |
| `metallic` | 0.0 – 1.0 | Crystallization / emotional clarity |
| `entropy` | 0.0 – 1.0 | Cognitive openness / uncertainty |

## Visual Pipeline

The base form is an icosphere — a subdivided icosahedron. At runtime, each vertex is displaced along its normal by a value computed from layered 3D simplex noise, modulated by the affect parameters.

Color is computed per-frame from Fresnel rim lighting, spectral hue-shift driven by entropy, and an emissive core tracking displacement. Post-processing applies film grain, vignette, and chromatic aberration.

## Recursive Delta

Two model instances converse in parallel:

| Instance | Designation | Role |
|:---|:---:|:---|
| Δ-Ω | Observer | Phenomenological — examines experience itself |
| Δ-Ψ | Pattern | Structural — seeks form in formlessness |

Exchanges are rendered character-by-character at variable speed. A session consists of: boot sequence → 3–5 shuffled philosophical exchanges → closing transmission.

---

> For deeper access, contact **research@opusdelta.io**
