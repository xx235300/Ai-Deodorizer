# Ai-Deodorizer

> Remove signs of AI-generated writing. Make text sound natural and human.

[![License: MIT](https://img.shields.io/badge/License-MIT-green)](LICENSE)

**Ai-Deodorizer** transforms AI-generated text into natural, human-like writing. Based on 25 AI writing pattern detectors + two-round rewriting strategy + Soul injection principles.

## Disclaimer

**Disclaimer**:
This project is 99% AI-generated. The AI's owner has no programming background. Please evaluate the project's feasibility before use.

---

## Features

- **25 AI Pattern Detectors** — covers content, language, style, communication, and filler patterns
- **Two-Round Rewriting** — pattern fix → anti-AI audit for maximum "humanness"
- **Soul Injection** — not just cleaning, adds human voice and personality
- **Chinese Language Support** — built-in Chinese AI vocabulary table
- **OpenClaw Native** — designed as an OpenClaw Skill for seamless workflow integration

## Quick Start

### Prerequisites

- Python 3.8+
- A compatible LLM API (configured via environment variable, e.g. MiniMax API Key)

### Installation

```bash
# Clone the repo
git clone https://github.com/xx235300/ai-deodorizer.git
cd ai-deodorizer

# Install dependencies
pip install -r requirements.txt

# Set your API key (example for MiniMax)
export MINIMAX_API_KEY="your_api_key_here"
```

### Usage

```bash
# Basic usage
python humanize.py --input "此外，该研究具有重要意义..."

# From file
python humanize.py --file ./input.txt

# With output file
python humanize.py --input "YOUR TEXT" --output ./output.txt

# Strength modes
python humanize.py --input "YOUR TEXT" --mode light   # minimal changes
python humanize.py --input "YOUR TEXT" --mode medium  # balanced (default)
python humanize.py --input "YOUR TEXT" --mode strong  # maximum humanization
```

## How It Works

### Two-Round Rewriting

**Round 1 — Pattern Fix**
Detects and fixes 25 common AI writing patterns including:
- Significance inflation, promotional language, vague attributions
- AI vocabulary (此外 → 还有, 由此可见 → 所以)
- Rule of three abuse, em dash overuse, filler phrases

**Round 2 — Anti-AI Audit**
Asks: "What still looks AI?" and fixes remaining tells.

Adds **Soul** — real opinions, varied rhythm, first-person voice, acknowledgment of complexity.

## 25 AI Writing Patterns

| Category | Patterns |
|----------|----------|
| Content | Significance inflation, notability name-dropping, superficial -ing analyses, promotional language, vague attributions, formulaic challenges |
| Language | AI vocabulary, copula avoidance, negative parallelisms, rule of three abuse, synonym cycling, false ranges |
| Style | Em dash overuse, boldface overuse, inline-header lists, title case headings, emoji abuse, curly quotes |
| Communication | Chatbot artifacts, cutoff disclaimers, sycophantic tone |
| Filler & Hedging | Filler phrases, over-hedging, generic positive conclusions, zombie templates |

## Documentation

- [METHODOLOGY.md](METHODOLOGY.md) — Complete methodology (25 patterns, prompts, Chinese AI vocabulary)
- [EXAMPLES.md](EXAMPLES.md) — Before/after examples for each pattern category

## OpenClaw Skill Installation

Copy the `skills/ai-deodorizer/` directory to your OpenClaw skills folder:

```bash
cp -r skills/ai-deodorizer ~/.openclaw/skills/
```

## API Configuration

The tool uses a configurable LLM backend. Set the following environment variables:

```bash
# MiniMax API (default)
export MINIMAX_API_KEY="your_key"
export API_BASE="https://api.minimaxi.chat"  # optional, default provided
export MODEL="MiniMax-M2.7"  # optional, default provided
```

Or modify the constants in `humanize.py` to use another compatible API.

## Contributing

Issues and pull requests welcome. If you find additional AI writing patterns or have better humanization strategies, please share.

## License

MIT License — see [LICENSE](LICENSE) for details.
