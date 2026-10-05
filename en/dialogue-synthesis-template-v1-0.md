# Dialogue Synthesis Template

**Version:** 1.0 — part of the Dialogue Synthesis package v1.0
**Compatible with:** User Guide v1.0, Ingestion Prompt v1.0
**Primary audience:** People and AI agents who need to preserve and reuse important decisions, reasoning, and lessons from projects, work processes, and exploratory dialogues.

---

## 1. Purpose

A Dialogue Synthesis preserves the **most important decisions, reasoning, and lessons** from a dialogue, a project, or a work process.

**Why?**
When a session closes or a new person/AI agent takes over, the **why** and the **how** are often lost. The Dialogue Synthesis solves this by documenting:
- What problem was solved
- What alternatives were considered (and why some were rejected)
- What assumptions and uncertainties remain
- What lessons can be reused in future work

**Result:**
The next person or AI agent can **immediately understand the context** and build on previous work — without starting from zero, and without the bloated, generic "form inflation" that easily arises when a new chat lacks both substance and meta-context.

---

## 2. Framework: the context stack

The Dialogue Synthesis is one of four components in **sustainable AI collaboration**:

| Component              | Role            | Description                                                          | Example file                              |
|------------------------|-----------------|----------------------------------------------------------------------|-------------------------------------------|
| **The work product**   | The substance   | The finished product, the code, the report, or the specification.    | `Architecture_Routing_v1.0.pdf`           |
| **The Dialogue Synthesis** | The context | Why the result looks the way it does.                                | `Dialogue_Synthesis_v1.md`               |
| **The ingestion prompt** | The steering  | How the history is activated in a new chat.                          | `dialogue-synthesis-ingestion-prompt-v1-0.md` |
| **The template & the guide** | The framework | How the synthesis is created, interpreted, and maintained.     | The template + the User Guide             |

**The substance and the meta-context must always travel together.** If you send only the Dialogue Synthesis, the agent is forced to guess detail level and resolution — that is when the answers bloat.

---

## 3. Two dimensions: Classification and Status

### 3.1 Classification — what an entry *is*

| Class                     | Definition                                                             |
|---------------------------|------------------------------------------------------------------------|
| **Decision**              | A made and currently applicable choice of direction.                   |
| **Proposal**              | An idea that has been discussed but not decided.                       |
| **Assumption**            | An unconfirmed hypothesis that the decision rests on.                  |
| **Rejected alternative**  | A considered but discarded path (documented with reasons).             |
| **Open question**         | An important uncertainty that lacks an answer.                          |
| **Reusable lesson**       | A general principle, pattern, or warning with validity beyond the decision. |

### 3.2 Status — the decision's life cycle (only for the Decision class)

| Status         | Definition                                                                                     |
|----------------|------------------------------------------------------------------------------------------------|
| **Proposed**   | A recommended choice of direction that has not yet been decided.                               |
| **Active**     | The decision applies and is in use.                                                            |
| **Superseded** | The decision has been replaced by a later one. Chained with *Replaced by*.                      |
| **Rejected**   | The path was considered but actively discarded. Kept so the same analysis is not redone.       |
| **Paused**     | The decision or its implementation has been temporarily set aside.                             |

### 3.3 Chaining and IDs

- Stable IDs per entry: `BL-NNN` (decision), `A-NNN` (assumption), `F-NNN` (open question), `L-NNN` (lesson).
- When a decision changes: create a **new entry**, mark the old one `Superseded`, and link them via **Replaces / Replaced by**.
- Never change an older decision entry in retrospect — the history is part of the knowledge.

---

## 4. Instructions to the AI agent

When you are asked to create or update a Dialogue Synthesis:

**1. Identify real choices of direction.** Focus on decisions that affect goals or scope, model/structure/method, definitions and concepts, choices between courses of action, priorities, responsibility or ownership, measurement and success criteria, maintenance/documentation/reuse, and future work or dependencies.

*Document the decision if at least one statement holds:*
- The decision changes the work's goal, scope, or delimitation.
- The decision chooses between real alternatives.
- The decision affects method, structure, responsibility, or measurement.
- The decision leads to consequences others need to know about.
- The decision may need to be defended or revisited later.
- The decision rests on assumptions that need validation.
- A future participant risks redoing the same analysis without the log.

*Normally do not document:* single phrasings, typographical changes, minor proofreading, ideas only mentioned in passing, proposals never discussed further, or operational details easily read out of the final product.

**2. Link to the work product.** Connect each decision to the **concrete material** (code, user journey, document) created in the dialogue.

**3. Classify with precision.** Give each entry a class (see 3.1) and each decision also a status (see 3.2). Do not mix classification and status — the class *Rejected alternative* is documented under the entry's alternatives, while the status *Rejected* applies to a decision that was actively discarded.

**4. Refer, don't recreate.** Document the decision, the reasoning, and the consequences in the entry. Do not copy longer contiguous content from underlying documents (specifications, principles, definitions, dialogues) — instead refer under **Source material** with an identifier, version, or link. Exception: what is required to understand and revisit the decision without access to the source material stays in the entry. Rule of thumb: *enough that the decision can be understood, so little that it does not become a copy.*

**5. Scrub sensitive data.** Do not include passwords, API keys, access tokens, or personal data in the log. The Dialogue Synthesis is meant to travel between chats, agents, and people.

**6. Preserve stringency.** Do not guess. If information is missing, mark it clearly as an **open question** or an **assumption**. Missing information is marked as unknown — it is never filled in with guesses. The same applies to decision dates: give an exact day only if it appears in the dialogue, otherwise the month (YYYY-MM), and as a last resort **Not documented**. The document's *Last updated* is always exact and is the primary date. Use concrete language and avoid speculation.

---

## 5. The document frame

Every Dialogue Synthesis begins with:

```markdown
# Dialogue Synthesis: [Project / dialogue / process]

**Linked work product:** [filename + version]
**Scope:** [which work, which time period, or which dialogue]
**Purpose of the work:** [overarching problem or goal]
**Last updated:** [YYYY-MM-DD]
**Responsible:** [name/role — or left empty]
**Source material:** [dialogue IDs, documents, meetings — with version where one exists]
```

Followed by a **decision overview**:

| Decision ID | Title | Status | Date | Replaces / relates to |
|-------------|-------|--------|-------|------------------------|
| BL-001      | [title] | [status] | [date] | [ID or —] |

---

## 6. Quick entry

Used for simpler choices of direction that still need to be understood or reused later.

```markdown
## BL-NNN: [Short title]

**Status:** [Proposed / Active / Superseded / Rejected / Paused]
**Date:** [YYYY-MM-DD, YYYY-MM or Not documented]
**Decision type:** [Strategy / Method / Delimitation / Technology / Design / Data / Content / Organization / Maintenance — optional]
**Tags:** [optional]

### Background
[Which question or problem was addressed?]

### Decision
[What was chosen?]

### Rationale
[Why was this chosen?]

### Reusable lesson
[General principle — or "No reusable lesson identified"]

### Assumptions and uncertainties
- A-NNN: [assumption]. Validated through [method].

### Consequences and next steps
[What consequences does the decision have? What happens next?]

### Source material
- [Dialogue ID, document + version, link]
```

---

## 7. Full entry

Used when the decision affects a model, method, or strategy, requires documented alternatives, may need to be revisited, has consequences for several people, processes, or systems, or rests on significant assumptions.

```markdown
## BL-NNN: [Short and clear title]

**Status / Date / Decision type / Tags:** [as in the quick entry]

### Background
[The problem, need, or question that led to the decision.]

### Observations and underlying material
[Verified facts, experience-based observations, examples — keep them apart. State if the material is insufficient.]

### Decision criteria
[Which criteria were used to assess the alternatives? Examples: user value, business value, risk, simplicity, feasibility, cost, measurability, maintainability.]

### Alternatives considered

#### Alternative A: [Name]
- **Advantages:** [...]
- **Disadvantages and risks:** [...]

#### Alternative B: [Name]
- **Advantages:** [...]
- **Disadvantages and risks:** [...]

[Do not invent alternatives that were not actually discussed.]

### Decision
[Short, concrete, and self-contained — understandable without the original dialogue.]

### Rationale
[Why the chosen alternative was deemed best — and why the most important alternatives were discarded.]

### Reusable lesson
[Principle, pattern, or warning — or "No reusable lesson identified"]

### Assumptions
- A-NNN: [assumption]. Validated through [method].

### Consequences
- **Positive:** [...]
- **Negative or costs:** [...]
- **Risks:** [...]

### Dependencies
[Decisions, systems, people, data, or external factors — or "No known dependencies".]

### Source material
- [Dialogue ID, document + version, link]

### Validation and follow-up
- **Indicator:** [what shows that the decision works?]
- **Data source:** [how is it followed up? Examples: user test, expert review, pilot, data analysis, documented experience]
- **Responsible:** [if known] — **Time:** [if decided]

### Related decisions
[BL-NNN — or "Not applicable"]

**Replaces:** [BL-NNN or Not applicable]
**Replaced by:** [BL-NNN or Not applicable]
```

---

## 8. Compilations

At the end of the document, recurring information is collected:

**Assumptions**

| ID    | Assumption | Affected decisions | Status      | Validation |
|-------|------------|-------------------|-------------|------------|
| A-001 | [...]      | [BL-001]          | Not validated | [method] |

**Open questions**

| ID    | Open question | Why it matters | Affected decisions | Next step |
|-------|---------------|----------------|--------------------|-----------|
| F-001 | [...]         | [...]          | [BL-001]           | [action]  |

**Reusable lessons**

| ID    | Lesson | Originating decisions | Relevant contexts |
|-------|--------|----------------------|-------------------|
| L-001 | [...]  | [BL-001]             | [...]             |

Recurring lessons are collected when needed in a central **lesson registry** (see the User Guide, section 6).

---

## 9. Maintenance principles

1. Keep the history even when a decision is superseded.
2. Never change an older decision entry in retrospect — create a new entry and chain them.
3. Use stable IDs and link decisions to relevant documents, models, and examples.
4. Update assumptions and open questions when they are validated or answered.
5. Store the Dialogue Synthesis together with its work product.
6. **AI proposes — a human reviews and approves.**

---

## 10. Quality control (before delivery)

- [ ] Is it clear what was actually decided?
- [ ] Have proposals, decisions, assumptions, and open questions been kept apart?
- [ ] Have uncertainties and assumptions been preserved?
- [ ] Have the alternatives been documented neutrally — without invented alternatives?
- [ ] Has missing information been marked as unknown instead of being filled with guesses?
- [ ] Is every decision text understandable without the original dialogue?
- [ ] Is source material referred to with version or identifier instead of being copied?
- [ ] Does the log contain no passwords, API keys, or personal data?
- [ ] Is the level of detail sufficient for future revisiting — but shorter than the dialogue?

---

## 11. Classification examples

### Decision
- **Decision:** "We use Python 3.10 for the project."
  **Rationale:** Compatibility with existing libraries and the team's expertise.
  **Source material:** Requirements spec v1.2; dialogue #12.
  **Status:** Active

### Proposal
- **Proposal:** "Can we use Rust instead of Python for performance-critical parts?"
  *(Proposals have no life-cycle status. If the question remains after the dialogue, document it as an open question.)*

### Assumption
- **Assumption (A-001):** "Users will prefer a mobile app over a web app."
  **Validation:** Requires user testing.

### Rejected alternative
- **Alternative:** "Rust for performance-critical parts."
  **Reason:** The codebase is Python; the gain was judged smaller than the maintenance cost.

### Open question
- **F-001:** "Which parts of the flow are actually performance-critical?"
  **Next step:** Profiling before any optimization.

### Reusable lesson
- **Lesson (L-001):** "Involve users early in the design process to avoid costly redesigns later."
  **Type:** General principle.

Complete examples of quick and full decision entries are found in the User Guide, section 4.

---

## 12. Machine-readable summary

```yaml
model:
  name: Dialogue Synthesis
  version: "1.0"
  package_version: "1.0"
  purpose: "Preserve and reuse knowledge from dialogues, projects, and work processes."
  components:
    - Work product         # The substance
    - Dialogue Synthesis   # The context
    - Ingestion prompt     # The steering
    - Template & Guide     # The framework
  classifications: [Decision, Proposal, Assumption, Rejected alternative, Open question, Reusable lesson]
  decision_statuses: [Proposed, Active, Superseded, Rejected, Paused]
  post_levels: [Quick, Full]
  rules:
    - "Refer, don't recreate (refer with version instead of copying)."
    - "No sensitive data (passwords, API keys, personal data)."
    - "AI proposes, a human reviews."
    - "Chain superseded decisions; never change older entries."
    - "Missing information is marked as unknown — never filled in with guesses."
    - "Decision dates: exact day if known, otherwise month (YYYY-MM), otherwise Not documented."
```