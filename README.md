<img width="1280" height="640" alt="git (1)" src="https://github.com/user-attachments/assets/8920b256-2ba8-4988-b824-5351134eb4bd" />

# The Heart Circuit 🫀⚡

## Basic Details
### Individual Team

### Team Members
- Team Lead: Abhishek Jijo, Sahrdaya College of Engineering and Technology, Kodakara


### Project Description
The Heart Circuit is a browser-based "should I text her?" oracle that trains a real logistic regression model, live, in front of you, on sixty entirely fictional past attempts to close the loop. Set your dials — hour, mood, moonlight, battery, zodiac compatibility — and let a breadboard of pure longing decide your fate.

### The Problem (that doesn't exist)
Nobody has ever needed a rigorously engineered decision-support system to know whether to send "hey" at 1am. And yet, here we are, treating a crush like a control system that just needs the right feedback loop.

### The Solution (that nobody asked for)
We built an actual gradient-descent-trained logistic regression classifier — knobs, sliders, a battery gauge, an analog clock, a live loss curve and all — that ingests your vibes as numerical features and outputs a verdict: **Close the Circuit** or **Leave It Open Tonight**. For scientific integrity (and because love isn't actually predictable), the final call is secretly a coin flip.

## Technical Details
### Technologies/Components Used
For Software:
- HTML5, CSS3, JavaScript (vanilla, no build step)
- Logistic regression implemented from scratch (manual gradient descent, no ML libraries)
- SVG for the rotary knobs, wire slider, analog clock, and live loss chart
- Glassmorphism / iOS-inspired UI, all in a single self-contained `.html` file

For Hardware:
- None — this is 100% a software "circuit," no actual soldering was harmed

### Implementation
For Software:

# Installation
No installation needed — it's a single static HTML file.
```bash
git clone https://github.com/abhishek524671-alt/heart_circuit.git
cd heart_circuit
```

# Run
```bash
# just open it in a browser
open index.html        # macOS
start index.html       # Windows
xdg-open index.html    # Linux
```
Or double-click the file. No server, no dependencies, no npm install required.

### Project Documentation
For Software:

# Screenshots (Add at least 3)
![Signal log](screenshots/1-signal-log.png)
*The landing state. Stage 01 holds the model's entire worldview: sixty fictional past
attempts to close the loop, each logged across eight signal lines — hour, day, hours since
her reply, your average reply time, moonlight, zodiac compatibility, battery and how many
times you reopened the chat — ending in CONNECTED or OPEN CIRCUIT.*

![Input dials, part one](screenshots/2-inputs-a.png)
*Stage 03, upper half. The date defaults to tonight and recalculates day-of-week and
moonlight when changed; the hour is an analog dial read off the system clock and draggable
by hand; hours-since-her-reply and your average reply time are beads dragged along copper
traces.*

![Input dials, part two](screenshots/2-inputs-b.png)
*Stage 03, lower half. Battery is a draggable capacitor gauge — reading 39% live off the
device here — beside a rotary knob counting chat re-dials, then the two zodiac selects and
tonight's moonlight, which is computed and deliberately not editable.*

![Verdict](screenshots/3-verdict.png)
*The readout. "Leave it open tonight," 79.2% confidence, with a circuit analysis naming the
three features that moved the number most — 99% moonlight, a zodiac compatibility of 88,
and a 15-minute average reply time. Every reading is kept in the session log below.*

# Diagrams
```mermaid
flowchart TD
    A[60 fictional past attempts<br/>8 features each] --> B[Standardize<br/>zero mean, unit variance]
    B --> C[Logistic regression<br/>full-batch gradient descent<br/>300 epochs, BCE loss]
    C --> D[Learned weights + bias]
    C --> E[Live loss curve<br/>+ feature importances]
    F[Your dials tonight<br/>hour, moon, battery,<br/>zodiac, re-dials...] --> G[Feature vector]
    D --> H[Sigmoid inference]
    G --> H
    H --> I[Ranked feature contributions<br/>-> reasoning text]
    I --> J[Verdict:<br/>Close the Circuit /<br/>Leave It Open Tonight]
    K[Coin flip] -.->|overrides the model| J
```

*Data → training → inference → verdict. Every stage is real except the last arrow: the model
genuinely trains and genuinely ranks which of your inputs mattered, then a coin flip decides
the actual answer. The reasoning you get is a true explanation of a prediction that was never
consulted.*

### Project Demo
# Video
[Add your demo video link here]
*Demonstrates setting the dials, training the model live, and getting roasted by your own heart circuit.*

# Additional Demos
[Add any extra demo materials/links]

## Team Contributions
- Abhishek Jijo: Sole developer — designed, built and shipped the entire project.
  Implemented the logistic regression from scratch: feature standardisation, full-batch
  gradient descent over 300 epochs, binary cross-entropy loss, and the per-feature
  contribution ranking that drives the reasoning text. Hand-rolled every instrument in SVG
  rather than using form inputs — the rotary re-dial knob, the draggable analog hour dial
  with AM/PM, the bead-on-a-copper-trace sliders, the capacitor battery gauge (wired to the
  live Battery Status API where the browser exposes it) and the animated loss chart. Wrote
  the lunar-phase approximation and zodiac-element compatibility scoring that turn vibes
  into feature vectors, the reasoning and roast generators, and the glassmorphism UI. Packaged
  the whole thing as one self-contained HTML file with no build step, no dependencies and no
  network calls.

---
Made with ❤️ at TinkerHub Useless Projects

![Static Badge](https://img.shields.io/badge/TinkerHub-24?color=%23000000&link=https%3A%2F%2Fwww.tinkerhub.org%2F)
![Static Badge](https://img.shields.io/badge/UselessProjects--26-26?link=https%3A%2F%2Ftinkerhub.org%2Fevents%2F1M8ORET9A1%2Fuseless-projects-3.0)
