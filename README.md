# Regex → Automata Converter

An interactive, single-page web application that converts regular expressions into finite automata (ε-NFA and DFA) with real-time D3.js force-directed graph visualizations.

---

## Features

- **Regex to ε-NFA conversion** using Thompson's Construction algorithm
- **NFA to DFA conversion** via the Subset Construction (Powerset) algorithm
- **Interactive D3.js graph visualization** with force physics simulation
- **String simulation** — test whether an input string is accepted or rejected, with a full state-trace
- **Transition tables** for both NFA and DFA
- **Theory tab** — built-in reference covering automata theory, algorithms, and regex syntax
- **Export options** — download the diagram as an SVG file or copy it as Graphviz DOT notation
- **Light / Dark theme toggle**
- **Display options** — toggle ε-moves visibility, physics simulation, node labels, and curved edges

---

## Supported Regex Syntax

| Syntax | Meaning |
|--------|---------|
| `a·b` | Concatenation (implicit) |
| `a \| b` | Union / alternation |
| `a*` | Kleene star — zero or more |
| `a+` | One or more |
| `a?` | Zero or one (optional) |
| `(…)` | Grouping / precedence |

---

## Getting Started

This is a **zero-dependency, single-file** application. No build step or server is required.

1. Clone or download the repository.
2. Open `index.html` in any modern web browser.
3. Type a regular expression (e.g. `(a|b)*abb`) into the input field and click **Convert** (or press `Enter`).
4. The ε-NFA graph will render immediately. Switch between **ε-NFA**, **DFA**, **Table**, and **Theory** tabs using the header navigation.

---

## Usage

### Converting a Regex
- Type a regex in the input field, or click one of the **quick-example chips** (`(a|b)*abb`, `a*b+`, `(0|1)*00`, etc.).
- Click **Convert** or press `Enter`.
- The NFA and DFA are built automatically and displayed in the canvas area.

### Navigating Views
| Tab | Description |
|-----|-------------|
| **ε-NFA** | Force-directed graph of the nondeterministic automaton |
| **DFA** | Force-directed graph of the equivalent deterministic automaton |
| **Table** | Transition tables for both the NFA and DFA |
| **Theory** | Reference cards covering automata theory, Thompson's Construction, and Subset Construction |

### Canvas Controls
- **Pan** — click and drag the background
- **Zoom** — scroll wheel
- **Move nodes** — drag individual state nodes
- **Toolbar buttons** — fit to screen, zoom in/out

### Simulating a String
1. Enter a test string in the **Simulate Input** field.
2. Click **Run** or press `Enter`.
3. The result shows **ACCEPTED** or **REJECTED**, along with a full state-path trace.

### Display Options
| Option | Effect |
|--------|--------|
| Show ε-moves | Toggle visibility of epsilon transitions |
| Physics sim | Enable / disable D3 force simulation |
| Show labels | Toggle state and transition labels |
| Curved edges | Switch between curved and straight transition arrows |

### Exporting
- **DOT** — copies the NFA in Graphviz DOT format to the clipboard
- **SVG** — downloads the current canvas as an `automata.svg` file

---

## Technology Stack

| Technology | Purpose |
|------------|---------|
| HTML / CSS / JavaScript | Single-file app, no framework |
| [D3.js v7](https://d3js.org/) | Force-directed graph rendering |
| [Space Mono & DM Sans](https://fonts.google.com/) | Typography (via Google Fonts) |

---

## Algorithms

**Thompson's Construction** — Converts a regular expression into an ε-NFA by recursively building sub-automata for each operator (concatenation, union, Kleene star, `+`, `?`) and combining them with ε-transitions.

**Subset Construction (Powerset)** — Converts the ε-NFA to a DFA by computing ε-closures and grouping sets of NFA states into single DFA states.

---

## Browser Compatibility

Works in all modern browsers that support ES6+ and SVG. No installation or internet connection required beyond the initial load of Google Fonts and D3.js from CDN.

---

## License

This project is provided as-is for educational purposes.
