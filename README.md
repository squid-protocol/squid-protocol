# Hi, I'm Joe Esquibel, Ph.D.

**Independent R&D engineer: program analysis, legacy modernization, and computational research.**

I'm a tenured biology professor and pharmacology researcher who taught myself software engineering over ~20 years of
increasingly computational work. Now I build tools for hard technical problems, where the standard tools aren't quite
enough and the interesting part is finding the right abstraction.

📧 **[joe@gitgalaxy.io](mailto:joe@gitgalaxy.io)** · open to R&D contracts, modernization work, and commercial licensing of GitGalaxy

---

## [GitGalaxy](https://github.com/squid-protocol/gitgalaxy): BLAST for source code

<a href="https://github.com/squid-protocol/gitgalaxy"><img src="https://raw.githubusercontent.com/squid-protocol/gitgalaxy/main/docs/media/scan-flow-rainbow.gif" width="100%" alt="One real GitGalaxy scan, start to finish: pip install gitgalaxy and galaxyscope in a terminal, the repository's files as tiles coloured by language, the files left out at each gate with their reasons, every language read by one engine, and the seven reports it writes, on a real-time clock"></a>

<sub>One real scan, start to finish: every number is from the scan's own output, and the clock is its real wall time.</sub>

**[Website](https://gitgalaxy.io) · [PyPI](https://pypi.org/project/gitgalaxy/) · [Documentation](https://squid-protocol.github.io/gitgalaxy/) · [Demo video](https://www.youtube.com/watch?v=XWWSd8LmoCM)**

As a scientist I used BLAST every day. It finds a gene's relatives across millions of DNA sequences in seconds by
matching short words, without first working out what the gene does. GitGalaxy applies the same idea to code. It breaks
every function, in every language, into the same structural words, with no compiler, no build, and no AI model. That
makes code comparable across languages, repositories and decades, and it works on code that doesn't even build.

One scan of a repository gives you an architecture brief for engineers and AI agents, a call and import graph, SARIF, a
CycloneDX SBOM, and a queryable SQLite knowledge graph.

**Results, each with its source:**

| | |
|---|---|
| **59 languages** read down to the function | [the full list](https://github.com/squid-protocol/gitgalaxy#languages) |
| **100% validated function precision** vs Tree-sitter, across the 31 languages it can compare | [audit of 2026-08-30](https://github.com/squid-protocol/gitgalaxy/blob/main/docs/self_scan/tri_comparison_README.md) |
| **86.7–100% call-link precision** in 8 languages, vs compiler-grade reference analysers; recall is the open gap | [graph accuracy](https://github.com/squid-protocol/gitgalaxy/blob/main/docs/graph_accuracy.md) |
| **Kubernetes (2.46M lines) in about 65 s**; most repositories in under a second | [single run, 2026-09-19](https://github.com/squid-protocol/gitgalaxy-raw-output) |

The limits are published next to the results: the numbers come from our own pinned benchmark corpora, and
[the known blind spots](https://github.com/squid-protocol/gitgalaxy/blob/main/docs/known_blind_spots.md) are listed.
We also pre-registered a test of whether code structure predicts defects. [It doesn't](https://github.com/squid-protocol/temporal-crucible); change history does.

### Study: DOOM's DNA

<a href="https://github.com/squid-protocol/gitgalaxy/blob/main/docs/wiki/museum-of-code/teardown-of-doom.md"><img src="https://raw.githubusercontent.com/squid-protocol/gitgalaxy/main/docs/media/doom-ports.gif" width="100%" alt="DOOM's DNA: 16 programs on one chart, each showing how much of the original linuxdoom's wiring between its 16 parts it kept, against the same program shuffled as a chance baseline. C copies and the Scheme and Go translations keep the most; Java, Kotlin and C# keep none; rewrites from scratch and unrelated programs score no better than chance"></a>

How much of the original game's design survives when DOOM is ported to another language? GitGalaxy mapped
linuxdoom's 16 parts (777 functions, 1,605 calls), then measured 16 programs against a shuffled baseline. The Scheme
and Go translations kept as much of the wiring as the closest C copy. Java, Kotlin and C# kept none, and rewrites
from scratch score no better than chance. It measures code shape, not gameplay, and functions are assigned to parts by
name, so it isn't a blind test. [Read the study](https://github.com/squid-protocol/gitgalaxy/blob/main/docs/wiki/museum-of-code/teardown-of-doom.md).

## Current R&D: CICS and COBOL to Java, with the evidence

Most AI modernization asks a model to translate a whole legacy application and hopes for the best. I'm building the
opposite: a translator that ports CICS and batch COBOL by fixed rules, with no AI model writing the Java. Each ported
program is then checked against the original COBOL on the same inputs for byte-identical output.

Every program gets an evidence record and a level, from L0 (inventoried) to L5 (every surviving mutant accounted for).
[Current levels](https://github.com/squid-protocol/gitgalaxy/blob/generated/docs/language_status/progress.md) are
regenerated from the code. The comparison runs on GnuCOBOL, not on a real z/OS mainframe, and I say so wherever I report
a level.

The question behind it: **how much of software transformation can be made deterministic before probabilistic AI is introduced?**

## [squid-bot](https://github.com/squid-protocol/squid-bot): a coding fleet that runs itself

GitGalaxy is largely built by a fleet of AI coding agents, and squid-bot is what keeps that fleet safe to run. I set the
goals as an ordered list of issues. squid-bot starts agents only when the machine, the CI queue and the budget can take
them, and gives each one its own isolated copy of the repo. Every change is screened, cheap checks first and the full
test suite after, and only green changes are merged. When only a human can decide something, the question goes to my
phone and the fleet keeps working on everything else.

It reports its own costs as well as its output. From Oct 19 to 25 it merged 926 small PRs that closed 193 work items.
Its first two weeks cost about $2 per merged PR and $11 per resolved issue. [The live dashboard](https://github.com/squid-protocol/squid-bot#-live-fleet-dashboard)
also tracks CI load, how often `main` broke, and what is limiting the fleet each hour.

## How I work

I turn hard questions into fast, reproducible experiments. LLMs write most of my first drafts (through squid-bot). Whether a
change stays is decided by tests, reference oracles, benchmark corpora and CI gates, and I make every claim checkable in public:

- **[Raw output](https://github.com/squid-protocol/gitgalaxy-raw-output)**: unedited scans of hundreds of real repositories
- **[Language Crucible](https://github.com/squid-protocol/language-crucible)** and **[Keyword Rosetta](https://github.com/squid-protocol/keyword-rosetta)**: the benchmark and cross-language control corpora behind the numbers above
- **[COBOL → Java examples](https://github.com/squid-protocol/cobol_to_java_examples)**: 10 COBOL repositories (as of 2026-11-04) translated into compiling Spring Boot projects
- **[Population analyses](https://github.com/squid-protocol/gitgalaxy-population-analyses)** and **[telemetry](https://github.com/squid-protocol/squid-telemetry)**: statistics over the scan population, and public usage numbers

> **If I make an interesting claim, I want the machinery needed to investigate it to be public.**

Teaching shaped this. A decade in the classroom trained me to break complicated systems into models people can follow,
and to keep asking *"what evidence would convince us?"* ([teaching portfolio](https://github.com/squid-protocol/teaching-portfolio), with 40+ student testimonials).

## Classroom science games

I still build for the classroom: phone games a whole class can play together in a few minutes, each built around one
idea students usually only hear about.

<table>
<tr>
<td width="50%" valign="top">
<a href="https://glucose.fastmathfacts.io/"><img src="assets/glucose-game.png" width="300" alt="Cellular Respiration: The Game. Students join their class game with a 4-letter code, then move glowing electron pairs out of glucose into NADH and FADH2 and turn their energy into 38 ATP"></a>

**[Cellular Respiration: The Game](https://glucose.fastmathfacts.io/)**: students join on their phones with a class code and race to pull the energy out of glucose, moving electron pairs into NADH and FADH₂ and turning them into 38 ATP. Built for my intro biology course. You can also play alone against two computer cells.
</td>
<td width="50%" valign="top">
<a href="https://sixthsense.fastmathfacts.io/"><img src="assets/sixthsense.gif" width="220" alt="Sixth Sense: two stick figures, a watcher and a watched person facing a wall, each holding a phone. When the watcher looks and the watched person holds the button, it shows a match; when only the watcher looks, a miss. Timing bars fill below"></a>

**[Sixth Sense](https://sixthsense.fastmathfacts.io/)**: can you feel someone staring at your back? Two people, two phones: one holds a button while looking, the other while they feel watched. The real lesson is telling an effect from luck. Each run is scored against 999 bots that press the same way at random times, a permutation test explained in one sentence.
</td>
</tr>
</table>

## Other things I've built

<sub>Click a picture for its demo video.</sub>

<table>
<tr>
<td width="50%" valign="top">
<a href="https://www.youtube.com/watch?v=VSIW91JPdyw"><img src="https://img.youtube.com/vi/VSIW91JPdyw/0.jpg" width="220" alt="Helping Farmers Farm demo video"></a><br />
<strong><a href="https://github.com/squid-protocol/help_farmers_farm">Helping Farmers Farm</a></strong>: volunteer scheduling, farm management and digital waivers for work-share CSA farms. <strong>Used by a farm for 3+ years.</strong> <a href="https://www.helpingfarmersfarm.com">Website</a>
</td>
<td width="50%" valign="top">
<a href="https://www.youtube.com/shorts/_lPySIKtxEk"><img src="https://img.youtube.com/vi/_lPySIKtxEk/hqdefault.jpg" width="220" alt="Meow Turtle sorting machine demo video"></a><br />
<strong><a href="https://github.com/squid-protocol/meow-turtle">Meow Turtle</a></strong>: distributed control over RS-485, with an async Python digital-twin host driving bare-metal MicroPython nodes in a small-parts sorter. 
</td>
</tr>
<tr>
<td width="50%" valign="top">
<a href="https://www.youtube.com/watch?v=e0uPb7Tg9FI"><img src="https://img.youtube.com/vi/e0uPb7Tg9FI/0.jpg" width="220" alt="Sorting evolution algorithm demo video"></a><br />
<strong><a href="https://github.com/squid-protocol/sorting_evolution_algorithm">Sorting evolution</a></strong>: genetic algorithms over headless physics simulation to design the vibrating sorters Meow Turtle now runs. 
</td>
<td width="50%" valign="top">
<a href="https://youtube.com/shorts/G3fbgRJeNOc"><img src="https://img.youtube.com/vi/G3fbgRJeNOc/0.jpg" width="220" alt="Fast Math Facts demo video"></a><br />
<strong><a href="https://fastmathfacts.io/">Fast Math Facts</a></strong>: math practice that separates mastery from effort, with millisecond timing and an international leaderboard. <a href="https://fastmathfacts.io/">Website</a>
</td>
</tr>
</table>

## What I'm looking for

Hard, poorly solved problems in **program analysis, legacy modernization, AI/LLM systems, and scientific computing**: the ones where nobody yet knows the best way to solve them.

**I'm curious by default, and I really like finding out whether an idea actually works.**

📧 **[joe@gitgalaxy.io](mailto:joe@gitgalaxy.io)**
