# Non-linear Pendulum Simulation — Teaching Artifact

**INT6064 Coding & Computational Thinking — Group Project 6**

A browser-based pendulum laboratory for Secondary 3 (Grade 9) students. Students set the
pendulum length, release angle and gravitational acceleration, run the simulation, and
compare the simulated period with the value predicted by the small-angle formula
`T = 2π√(L/g)`. At a release angle of 39.62° the simulation gives 2.749 s against a
predicted 2.667 s — a deviation of about **3.0%** that grows as the angle increases.

The point of the artifact is that this deviation is **measured, not asserted**. Real
apparatus cannot show it: friction damps a large-amplitude swing before its period can be
timed, and stopwatch error is larger than the effect.

---

## Files

| File | What it is |
|------|------------|
| `pendulum_simulation.html` | **The artifact.** A single self-contained page — open it in any browser, no installation, no network, no account. |
| `pendulum_simulation.py` | **The codebase.** The Python script that generates the HTML. Standard library only. |
| `README_zh.txt` | The original usage notes (Chinese). |

---

## How to run

**As a student would:** double-click `pendulum_simulation.html`. Everything — the
simulation, the plots and the language resources — is embedded in that one file.

**To modify it:** edit `pendulum_simulation.py`, then

```
python pendulum_simulation.py
```

which regenerates `pendulum_simulation.html` under the same name. Refresh the browser to
see the change.

---

## What it does

- Sliders for **length**, **release angle** and **gravity** (Earth 9.81 m/s², switchable to
  Moon 1.62 m/s²)
- Live swing animation and an **angle–time waveform**
- Automatic readout of the **simulated period** beside the **small-angle prediction**
- **Pause**, **step 0.02 s**, **reset**
- **Four sequential inquiry booklets** that require a written prediction before each run;
  booklet 2 locks its forecast once the simulation starts
- **CSV export** of trial data, and **JSON backup/restore** of the whole exploration
- Three interface languages: Simplified Chinese, Traditional Chinese, English
- Progress is saved in the browser, so a class can stop and resume

---

## Computational thinking

| Practice | Where it appears |
|----------|------------------|
| Decomposition | Length, release angle and gravity are separated and varied one at a time |
| Pattern recognition | Period is compared with angle across trials |
| Abstraction | The idealised small-angle formula is set against non-linear behaviour |
| Algorithmic procedure | Predict → Adjust → Observe → Explain, enforced by the four booklets |
| Evaluation | Students judge where the model stops being adequate |

---

## Requirements

- Any modern browser (the artifact)
- Python 3.8+ with the standard library only (the generator)

---

## Known limitation

The simulation is **undamped**. Real pendulums lose amplitude, so students may leave
believing a pendulum swings forever. This is a deliberate simplification of the model and
is used in class as the starting point for a discussion about what a computational model
leaves out — adding a damping control is the next planned improvement.

Booklets 3 and 4 (the gravity comparison and the model-evaluation task) are designed as
follow-up lessons beyond the 45-minute core.
