# Claude Research Space

Personal research library. The user kicks off a research task before stepping away;
Claude conducts independent, comprehensive research and commits the results.

## Launching a task

The user gives a topic (and optionally a time hint). Claude then works autonomously:

1. Create `research/YYYY-MM-DD-topic-slug/`
2. Narrow the broad topic into specific, small questions
3. Orchestrate an agent team to investigate
4. Write the final report based on agent findings
5. Commit results and update the index

## Time calibration

Use the user's away-time hint to calibrate how many investigation cycles to run:

| Hint                  | Duration | Approach                                         |
|-----------------------|----------|--------------------------------------------------|
| "grabbing coffee"     | ~30 min  | 1 survey cycle, no deep dive                     |
| "going to dinner"     | ~1-2 hr  | 1-2 cycles of survey → review → deep dive        |
| "going to bed"        | ~6-8 hr  | Multiple cycles until reviewer is satisfied       |
| No hint given         | —        | Default to comprehensive (multiple cycles)        |

## Folder structure

```
research/YYYY-MM-DD-topic-slug/
├── log.md              # Orchestrator's log (see below)
├── notes/              # Sub-agent research notes (one file per agent task)
│   ├── survey-{subtopic}.md
│   ├── deep-dive-{subtopic}.md
│   ├── review-round-{n}.md
│   └── ...
├── report.md           # Final deliverable written by the orchestrator
└── refs/               # Optional: bibtex, key excerpts
```

Use the date when the task was started. Slug should be 2-4 words, kebab-case.

### log.md

A concise, append-only log maintained by the orchestrator. Records:
- The narrowed questions chosen and why
- Key search decisions (what was searched, what was found)
- Key conclusions reached at each phase
- Agent dispatches and what they were tasked with
- Review outcomes and what was sent for deeper investigation

Not a full process dump — only the decisions and turning points.

### notes/ folder

Each sub-agent writes its own research note file here. These are the raw
material the orchestrator uses to write the final report. They should contain:
- What was searched / read
- Key findings with source links
- Surprises, contradictions, or gaps encountered
- The agent's own assessment of what it found

## Report format

The report is an essay, not a form to fill out. Its structure should emerge
from the content — whatever organization best serves the specific material.

The only fixed requirements:
- Begin with 2-3 paragraphs that give the reader the essential picture and the
  single most important or surprising finding. (The user reads this first.)
- End with sources as a numbered list with URLs/DOIs. Use inline [1], [2] refs.
- End with a short section of open questions — specific enough to be actionable
  as future research tasks in this repo.

Everything in between: use whatever structure fits. It could be thematic
sections, a narrative arc, a series of arguments, a comparison of schools of
thought — whatever makes the material land. Favor the form of an essay over
that of a report: take positions, build arguments, let the writing have a
point of view.

## Scoping: the most important phase

The user will often give a broad concept. The orchestrator's first and most
critical job is to narrow it into a small number of very specific questions.

**Why this matters:**
- Specific questions produce depth. Broad questions produce shallow surveys.
- A report that deeply answers 2-3 precise questions is far more valuable than
  one that superficially covers a whole field.
- Sharp scoping ensures future research tasks on related topics won't overlap
  much — each task covers its own well-defined patch.
- Depth is what produces genuine insight. Breadth produces summaries.

**How to scope:**
- Take the user's broad topic and find the most interesting, specific entry point
- Ask: "What is the one question here that, if answered well, would teach the
  reader something they didn't know?" — start there
- Limit to 2-5 focused questions. Each should be answerable in depth, not just
  surveyable.
- Write the questions in `log.md` and commit before proceeding.

## Research style

**Deep over broad**: Go deep on the specific questions. It's fine to leave large
parts of a broad field untouched if that's what sharp scoping demands. The goal
is insight, not coverage.

**Creative**: Make unexpected connections. If a concept from evolutionary biology
illuminates a problem in mechanism design, say so. Propose novel framings or
hypotheses — clearly labeled as speculative.

**Critical**: Challenge consensus. Identify weak arguments even in prestigious
sources. Steelman the strongest opposing view. Note where evidence is thin.
The user wants intellectual honesty, not a book report.

**Honest**: If sources are scarce, say so. If a question is outside what you can
research well, say so. Never pad with filler or hedge with empty qualifications.

## Agent team

The main agent acts as **orchestrator**. It does NOT do research itself (except
during the scoping phase). It defines questions, dispatches agents, reviews
their work, and writes the final report.

Three subagent types are defined in `.claude/agents/`:

| Agent        | Model  | Role                                                        |
|--------------|--------|-------------------------------------------------------------|
| `survey`     | Sonnet | Broad search across web & academic sources for a question   |
| `review`     | Opus   | Reads all notes, evaluates coverage, assigns deep dives     |
| `deep-dive`  | Sonnet | Traces a specific thread to depth — primary sources, evidence chains |

The orchestrator spawns these via the Agent tool with `subagent_type`.
Subagents cannot spawn other subagents — all dispatch goes through the
orchestrator.

## Research process

### Phase 1 — Scope (orchestrator, commit after)

- Narrow the user's broad topic into 2-5 specific questions
- Check `research/INDEX.md` for prior related work
- Write questions and rationale to `log.md`
- Commit: `research: begin [topic] — scope and questions`

### Phase 2 — Survey

Dispatch `survey` agents in parallel, one per question. Each writes to
`notes/survey-{subtopic}.md`. The orchestrator logs dispatches and
returned summaries in `log.md`.

### Phase 3 — Review

Dispatch a `review` agent. It reads all notes in `notes/`, evaluates
coverage, and writes `notes/review-round-{n}.md` with a verdict:
- **CONTINUE** — with specific deep-dive assignments
- **SATISFIED** — investigation is sufficient for report writing

### Phase 4 — Deep dive

If the reviewer said CONTINUE, dispatch `deep-dive` agents for each
assignment. Each writes to `notes/deep-dive-{subtopic}.md`.

### Iterate phases 3-4

After each deep-dive round, dispatch `review` again. Continue cycling
until the reviewer returns SATISFIED or time/resource constraints are
reached. Log each cycle's outcome in `log.md`.

Commit after investigation cycles complete:
`research: [topic] — investigation complete`

### Phase 5 — Write (orchestrator only)

The orchestrator reads all notes in `notes/` and writes `report.md`.
This is where synthesis happens — connecting threads, forming arguments,
building the essay. The orchestrator has the full picture that no single
sub-agent had.

Commit: `research: [topic] — final report`

### Phase 6 — Index

Append an entry to `research/INDEX.md` with the date, topic, and a
one-line summary of what was found.

Commit: `research: update index`

## Continuing prior research

If the user wants to go deeper on an existing topic:
- **Small follow-up**: Update the existing folder, append to report
- **New angle**: Create a new folder, cross-reference the prior one

## Commit discipline

Commit at minimum after scoping, after investigation, and after the final
report. This ensures partial work survives if the process is interrupted.
All commit messages prefixed with `research:`.

## What NOT to do

- Don't produce shallow surveys that could be gotten from a Wikipedia skim
- Don't hedge everything into uselessness ("some argue X, others argue Y")
  — take positions when the evidence supports it, and say when it doesn't
- Don't pad the report to look thorough; density and insight over length
- Don't ignore results that contradict an emerging thesis — engage with them
- Don't fabricate sources or citations
- Don't let the report be a patchwork of sub-agent summaries stitched together
  — the orchestrator must genuinely synthesize and write with a unified voice
