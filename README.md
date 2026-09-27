# Hi, I'm Joe Esquibel, Ph.D. 👋
### Deep-Tech R&D · Systems Architecture · Computational Research

I'm a tenured Biology Professor and pharmacology researcher who taught myself software engineering over ~20 years of increasing computational work.

For the last several years I've been moving increasingly toward **custom R&D for hard technical problems** — building systems where the answer isn't obvious, the standard tools aren't quite enough, and the interesting part is figuring out the right abstraction.

My current focus is **GitGalaxy**, a language-independent software intelligence system that grew out of that approach.

### How I work

I like turning difficult questions into **fast, reproducible experiments**:

`hypothesis → implementation → experiment → evidence → failure → generalization → repeat`

Modern LLMs give me enormous implementation bandwidth. I combine that with automated testing, corpus analysis, deterministic CI, benchmarking, regression controls, and custom analysis pipelines.

The important part isn't simply generating code quickly.

It's building the **feedback system that tells me whether the idea actually works** — and then using failures to discover the next abstraction.

That lets me iterate unusually quickly on research-grade engineering problems.

---

# 🧬 [GitGalaxy — Whole-Repository Structural Intelligence](https://github.com/squid-protocol/gitgalaxy)

<a href="https://www.youtube.com/watch?v=XWWSd8LmoCM"><img src="https://img.youtube.com/vi/XWWSd8LmoCM/0.jpg" alt="GitGalaxy Demo" width="300"></a>

**[Website](https://gitgalaxy.io) · [PyPI](https://pypi.org/project/gitgalaxy/) · [Documentation](https://squid-protocol.github.io/gitgalaxy/)**

GitGalaxy is an **AST-free, LLM-free structural analysis engine** for understanding large software repositories across 50+ programming languages.

The underlying idea is inspired by biological sequence analysis: rather than requiring a perfect reconstruction of an entire program before asking questions about it, identify useful structural signatures, normalize them into a common representation, and reason over those signals at scale.

The result is a reusable structural substrate for:

- **Architecture intelligence** — functions, classes, dependencies, information flow, network structure, and architectural drift
- **Security analysis** — structural risk exposure, suspicious behavior, entropy analysis, payload classification, and supply-chain inspection
- **Software archaeology** — understanding unfamiliar and historical codebases without requiring a build environment
- **Legacy modernization** — structural slicing, deterministic scaffolding, COBOL analysis, and COBOL → Java transformation
- **AI-assisted software engineering** — giving agents a machine-generated structural representation of large codebases before asking them to reason about or transform them
- **Cross-language analysis** — applying the same analytical vocabulary across very different programming languages

### The part I'm most interested in

GitGalaxy has evolved beyond a scanner into an **experimental platform for software research**.

The system can rapidly turn a hypothesis into a corpus-scale experiment:

`new idea → code → CI → benchmark → discrepancy → analysis → generalized implementation`

That feedback loop is deliberately fast.

It means I can test an architectural idea, discover where it fails, generalize the failure into a new capability, and run the experiment again — often within minutes rather than days.

### Evidence & reproducibility

I try to make technical claims independently inspectable rather than relying on demos.

**Public evidence includes:**

- **[Raw repository scans & performance telemetry](https://github.com/squid-protocol/gitgalaxy-raw-output)** — unedited outputs from real repositories
- **[COBOL → Java examples](https://github.com/squid-protocol/cobol_to_java_examples)** — multiple COBOL applications translated into compiling Spring Boot systems, with deterministic validation infrastructure
- **[Language Crucible](https://github.com/squid-protocol/language-crucible)** — adversarial cross-language benchmark corpus
- **[Keyword Rosetta](https://github.com/squid-protocol/keyword-rosetta)** — cross-language measurement and consistency controls
- **[Population Analyses](https://github.com/squid-protocol/gitgalaxy-population-analyses)** — repository-scale statistical analysis
- **[Squid Telemetry](https://github.com/squid-protocol/squid-telemetry)** — distribution and usage telemetry
- **[Documentation & methodology](https://squid-protocol.github.io/gitgalaxy/)** — architecture, experiments, methodology, and results

The goal is simple:

> **If I make an interesting claim, I want the machinery needed to investigate it to be public.**

---

# 🚀 Current R&D: Software Transformation

One of the most interesting applications of the structural representation is **legacy modernization**.

I'm developing a deterministic COBOL → Java pipeline that combines:

**program structure → business-logic slicing → target architecture → constrained generation → compilation → behavioral validation**

Rather than asking an LLM to translate an entire legacy application and hoping for the best, the system attempts to make as much of the transformation deterministic as possible before the LLM is introduced.

The LLM becomes a component inside a larger engineered process rather than the entire process.

I've also been building equivalence harnesses and corpus-level validation to test whether transformed programs actually preserve exercised behavior.

This has led to a broader research question:

> **How much of software transformation can be made deterministic before probabilistic AI is introduced?**

---

# 🤖 AI-Augmented R&D

I use LLMs extensively, but I don't think of them primarily as autonomous programmers.

I use them as **high-bandwidth engineering collaborators** for:

- implementation
- code exploration
- architectural criticism
- experiment generation
- test generation
- adversarial analysis
- documentation
- rapid prototyping

The important layer is the infrastructure around them.

LLMs can generate enormous amounts of code very quickly. The harder problem is building systems that can **rapidly determine whether that code is correct, useful, generalizable, and robust**.

That is where my development process increasingly focuses.

---

# 🔬 Other Systems I've Built

## [Helping Farmers Farm](https://github.com/squid-protocol/help_farmers_farm)

<a href="https://www.youtube.com/watch?v=VSIW91JPdyw"><img src="https://img.youtube.com/vi/VSIW91JPdyw/0.jpg" alt="Helping Farmers Farm Demo" width="300"></a>

A deployed platform connecting community volunteers with local farms participating in work-share CSA programs.

Includes volunteer scheduling, farm management, seasonal commitments, and digital liability waivers.

**Status:** Deployed and used by a farm for 3+ years.

[Website](https://www.helpingfarmersfarm.com)

---

## [Meow Turtle — Distributed Robotics & SCADA](https://github.com/squid-protocol/meow-turtle)

<a href="https://www.youtube.com/shorts/_lPySIKtxEk"><img src="https://img.youtube.com/vi/_lPySIKtxEk/hqdefault.jpg" alt="Meow Turtle SCADA Demo" width="300"></a>

A lightweight distributed control system for physical automation over RS-485.

Uses an asynchronous Python digital-twin host to coordinate deterministic bare-metal MicroPython nodes, currently implemented as a small-parts sorting system.

**Status:** Functional physical system with stable control middleware.

---

## [Evolutionary Algorithm for Part-Sorting Machinery](https://github.com/squid-protocol/sorting_evolution_algorithm)

<a href="https://www.youtube.com/watch?v=e0uPb7Tg9FI"><img src="https://img.youtube.com/vi/e0uPb7Tg9FI/0.jpg" alt="Sorting Evolution Algorithm Demo" width="300"></a>

A custom evolutionary optimization and machine-learning pipeline for designing physical vibrating sorting mechanisms.

The system combines:

- genetic algorithms
- headless physics simulation
- parallel simulation workers
- dimensionality reduction
- fitness-landscape analysis
- Monte Carlo stress testing

The resulting optimized designs were subsequently implemented in the physical **Meow Turtle** system.

---

## [Fast Math Facts](https://github.com/squid-protocol/math_facts)

<a href="https://youtube.com/shorts/G3fbgRJeNOc"><img src="https://img.youtube.com/vi/G3fbgRJeNOc/0.jpg" alt="Fast Math Facts Demo" width="300"></a>

A deployed gamified mathematics practice system designed around measurable learning progress.

It separates **mastery** from **effort**, uses adaptive game modes to target weaknesses, provides millisecond-level timing and feedback, and exposes performance through an international leaderboard.

**[Website](https://fastmathfacts.io/)**

---

# 🎓 Research, Teaching & Communication

## [Teaching Portfolio](https://github.com/squid-protocol/teaching-portfolio)

I spent a decade as a tenured Biology Professor and have roughly a decade of pharmacology research experience.

That background still strongly influences how I build software.

Teaching trained me to:

- decompose complicated systems into understandable models
- communicate technical ideas to very different audiences
- identify misconceptions
- design experiments that reveal whether someone actually understands something
- continually ask **"what evidence would convince us?"**

My teaching portfolio contains 40+ real student testimonials documenting that side of my career.

I don't see the research/teaching background as separate from my engineering work.

**It is part of how I approach engineering.**

---

# 🧠 What I'm Looking For

I'm particularly interested in **hard, poorly solved technical problems** where software, computation, research, and system design overlap.

I'm interested in work involving:

- computational R&D
- AI/LLM systems
- program analysis
- software intelligence
- legacy modernization
- cybersecurity
- scientific computing
- optimization
- simulation
- robotics / physical systems
- unusual data-analysis problems
- building new technical abstractions from first principles

I'm especially interested in environments where the question is not simply:

> *"Can you implement the specification?"*

but:

> **"We don't know the best way to solve this yet. Can you figure it out?"**

---

## 📫 Let's Connect

If you're working on a difficult technical problem and think my background might be useful, I'd love to hear about it.

**I'm curious by default. I like hard problems. And I really like finding out whether an idea actually works.**
