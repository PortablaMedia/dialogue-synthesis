# User Guide: Dialogue Synthesis

**Version:** 1.0 — part of the Dialogue Synthesis package v1.0
**Compatible with:** Dialogue Synthesis Template v1.0, Ingestion Prompt v1.0
**Purpose:** A practical handbook for preserving and reusing knowledge, reasoning and stringency in iterative work with AI agents and in human projects.

---

## 1. Introduction

### Purpose of this guide
This guide helps you document important decisions from dialogues between people, between people and AI agents, or between AI agents, in a structured way.

The goal is to preserve knowledge so that you, colleagues or future AI agents can understand:
- which problems have been addressed
- which decisions have been made
- why certain directions were chosen
- which assumptions and uncertainties remain
- which reusable lessons can be carried over to other contexts

### The core concept: the context stack
When working in long or split AI sessions, two problems often arise:
1. **Memory loss:** the AI agent loses the thread or summarises away important details.
2. **Form inflation & loss of precision:** when a new chat is started without the right background material, the AI agent tends to produce bloated, generic and less useful answers instead of maintaining the same sharp stringency as in the previous chat.

To solve this, the method builds on a **four-part context stack**:

```text
  [ 1. WORK PRODUCT   ] --> "The substance" (The code, the user journeys, the report from the previous step)
  [ 2. DIALOGUE SYNTHESIS ] --> "The meta-context" (The decisions, the rationale, the lessons)
  [ 3. INGESTION PROMPT ] --> "The steering" (Locked frames, stringency requirements, today's goal)
  [ 4. FRAMEWORK / TEMPLATE ] --> "The standards" (Instructions for maintaining and updating)
```

> **Why isn't the Dialogue Synthesis alone enough?**  
> The Dialogue Synthesis preserves *the reasoning* (the meta-context). But if the AI agent does not also get to see the actual *work product* (the substance), it is forced to guess the level of detail and resolution. That is when the answer text easily swells from 6 consistent points to 25 generic ideas. **The substance and the meta-context must always travel together.**

### Four parts of a decision entry
For every decision, four concepts are kept strictly separate:

- **Decision:** describes **what was chosen**.
- **Rationale:** describes **why the chosen alternative was judged to be best**.
- **Consequences:** describes **what the decision leads to in the current work**.
- **Reusable lesson:** describes **what other projects, teams or future AI dialogues can learn from the decision**.

A reusable lesson should express a principle, a pattern, a warning or a practical rule of thumb. It must not simply repeat the decision.

Example:
- **Decision:** Practical guides are prioritised on the blog during the quarter.
- **Rationale:** Earlier guides generated higher engagement than news posts.
- **Consequence:** The editorial calendar needs to change.
- **Reusable lesson:** When earlier content shows clear differences in user behaviour, content formats should be prioritised based on documented effect — but the conclusion needs to be revisited when the target audience or distribution channel changes.

### Classification and status — two different things
Every entry in a Dialogue Synthesis has a **class** (what the entry is): Decision, Proposal, Assumption, Rejected alternative, Open question or Reusable lesson.

In addition to its class, every **decision** has a **status** describing its life cycle: `Proposed`, `Active`, `Superseded`, `Rejected` or `Paused`. The definitions are found in the template (section 3) — this guide uses the same values.

### Who is this guide for?
- **Project managers** who want to document key decisions.
- **Content creators** developing strategies or guidelines.
- **Developers & architects** making technical choices.
- **AI users** who want to preserve knowledge and stringency across long dialogues with AI agents.

---

## 2. When should you use Dialogue Synthesis?

### Trigger points: when should you create a synthesis?
Create or update a Dialogue Synthesis when any of the following occurs:
- The dialogue has become **too valuable to lose** — you would be sorry if the thread disappeared.
- The context window is approaching **capacity**, or the chat is starting to feel saturated.
- A **session or phase ends** and the next step requires a new chat.
- A **milestone** has been reached and you want to lock in the decisions made.
- You need to **switch agent, tool or person** in the work.
- An earlier assumption has been **revisited**, or a delimitation has become important.

### Use the Quick version when:
- The dialogue is short or simple and contains a few decisions.
- The decision does not require documented alternatives, risk analysis or dependencies.
- You want to capture the key points quickly.
- The decision is narrow in scope but may still need to be understood or reused later.

*Examples:*
- Blog posts should normally be at most 500 words.
- A particular visual principle should be used consistently in a campaign.
- The newsletter should be published on Thursdays.

### Use the Full version when:
- The decision affects a model, method, architecture or strategy.
- Documented alternatives and comparisons are needed.
- The decision may need to be revisited later.
- The decision has consequences for several people, processes, systems or AI agents.
- The decision rests on significant assumptions that need validation.
- A future participant risks having to redo the same analysis without the log.

*Examples:*
- A particular AI model is chosen for a service.
- The project is delimited to a specific target audience or market.
- User experience is prioritised over short-term cost savings.

### What not to document
A simple test: only document decisions that a future participant may need to revisit. Individual wordings, minor proofreading and ideas that were never discussed further do not belong in the log — the template's granularity test (section 4) owns the full rules.

### When should a reusable lesson be documented?
Document a lesson when at least one of the following applies:
- the same insight can help another project
- a clear pattern has been identified
- a common mistake or risk has become visible
- an edge case has led to an important principle
- an earlier assumption has proved insufficient
- the lesson can help a future participant/AI agent avoid redoing the same analysis

Not every decision yields a general lesson. Write **No reusable lesson identified** when the decision is specific to the current case.

---

## 3. How do you use Dialogue Synthesis?

### Step 1: Choose a version
Use the criteria in section 2 to choose the Quick or Full version. The structures for both are found in the template (sections 6–7).

### Step 2: Fill in the Dialogue Synthesis (ending Chat 1)
- Ask the AI agent to summarise the dialogue using **Prompt 1** (see section 8).
- Link the decisions directly to your produced Work Product.
- **Refer to source material by file name and version — do not paste in longer text excerpts** from specifications, principles or dialogues. What is required to understand the decision belongs in the entry; the rest is left to the source.
- **Never include passwords, API keys or personal data** in the log — it is meant to travel between chats, agents and people.
- **Quick version:** Fill in background, decision, rationale, reusable lesson, assumptions, consequences and source material.
- **Full version:** Also fill in observations, decision criteria, alternatives, dependencies, risks and follow-up.

### Step 3: Review and approve
If an AI agent created the log, the principle is: **AI proposes, a human reviews**.

Check that:
- the decision text is understandable without the original dialogue
- the link to the concrete Work Product is clear
- assumptions and uncertainties are separated from the decision
- the status is correct (`Active`, `Proposed`, `Superseded`, `Rejected`, `Paused` — definitions in the template)
- the reusable lesson does not merely repeat the decision
- source material is referred to **by version or identifier** instead of being copied
- the log contains no passwords, API keys or personal data

### Step 4: Save and version
- Save the log as Markdown, for example `Dialogue_Synthesis_v1.md` alongside your result `Work_Product_v1.md`.
- Create a new version when the log or the work product is updated.
- Keep older decisions when they are superseded and mark them as `Superseded` — link them to the new decisions (see the template's chaining rules).

### Step 5: Start the next session (load into Chat 2)
When you start the next chat in the same project:
1. Upload **both** `Work_Product_v1.md` and `Dialogue_Synthesis_v1.md`.
2. Paste in the **Ingestion Prompt** (the file `dialogue-synthesis-ingestion-prompt-v1-0.md`) together with today's new goal.
3. The AI agent locks in the decisions made, takes open questions into account and maintains the same level of detail and stringency.

---

## 4. Practical examples

### Example 1: Quick version

```markdown
# Dialogue Synthesis: Blog content Q4 2026

**Linked Work Product:** Editorial_Calendar_Q4.md

## BL-001: Focus on practical guides

**Status:** Active  
**Date:** 2026-09-02  
**Decision type:** Content  
**Tags:** blog, strategy, user experience

### Background
We wanted to increase traffic and engagement on the blog. Analysis of earlier posts showed that practical guides had significantly higher sharing than news posts.

### Decision
We prioritise practical guides and step-by-step articles during Q4 2026 (see module 2 in Editorial_Calendar_Q4.md).

### Rationale
Earlier results indicate higher engagement and better search performance for practical content.

### Reusable lesson
When earlier content shows clear differences in user behaviour, editorial planning should build on documented effect. The conclusion needs to be revisited if the target audience, topic or distribution channel changes.

### Assumptions and uncertainties
- A-001: Readers prefer practical content over news. To be validated through analysis of traffic data after three months.

### Consequences and next steps
- Write two guides per month.
- Update the editorial calendar.
- Follow up on time on page and shares.

### Source material
- Dialogue #45, analysis of blog statistics.
```

---

### Example 2: Full version

```markdown
# Dialogue Synthesis: AI chatbot for customer service

**Linked Work Product:** Architecture_Routing_v1.0.pdf

## BL-001: Choice of AI model and routing logic

**Status:** Active  
**Date:** 2026-08-15  
**Decision type:** Technology  
**Tags:** AI, model selection, performance, cost

### Background
An AI model was needed to handle Swedish customer questions about returns. The requirements covered accuracy, response time and cost.

### Observations and source material
- Model A gave lower cost and shorter response time but lower accuracy.
- Model B gave higher accuracy but higher cost and longer response time.
- Local models required more infrastructure and adaptation.

### Decision criteria
- accuracy, cost, response time, support for Swedish.

### Alternatives considered

#### Alternative A: Primary cost-effective model with a fallback model
- **Advantages:** Lower average cost and short response time.
- **Disadvantages and risks:** Requires logic to identify complex questions.

#### Alternative B: One more capable model for all questions
- **Advantages:** Simpler technical solution and higher average accuracy.
- **Disadvantages and risks:** Higher cost and longer response time.

### Decision
Use a cost-effective model as the primary model and a more capable model as fallback for complex questions (implemented according to the specification in Architecture_Routing_v1.0.pdf).

### Rationale
The solution was judged to give the best balance between cost, performance and language support, provided the fallback logic works reliably.

### Reusable lesson
Choosing an AI model does not have to be a binary choice between quality and cost. A combination of models can be appropriate when tasks vary in complexity, but the benefit depends on validating the classification and fallback logic.

### Assumptions
- A-001: The primary model handles the vast majority of questions well enough.
- A-002: Complex questions can be identified and passed on to the fallback model.

### Consequences
- **Positive:** Lower costs and shorter response time for most questions.
- **Negative:** Increased technical complexity.
- **Risks:** Misclassification can affect the customer experience.

### Dependencies
- Access to both models.
- A working router component for uncertain questions.

### Source material
- Test dialogues and requirements documents.
```

---

## 5. FAQ & Troubleshooting

### Why did the answer in Chat 2 become bloated and incoherent?
This is almost always due to **"form inflation"**, which occurs when the AI agent lacks the actual Work Product. If the AI only gets the decision text without the concrete draft/code, it is forced to guess the level of detail.
- **Solution:** Upload *both* the Work Product and the Dialogue Synthesis in Chat 2 — and use the Ingestion Prompt, which contains an explicit stringency requirement.

### What is the difference between a decision, a proposal, an assumption and a lesson?
- **Decision:** A choice that has been made and applies.
- **Proposal:** An idea that has been discussed but not settled.
- **Assumption:** An unconfirmed hypothesis that the decision rests on.
- **Reusable lesson:** A general principle, pattern or warning that can be applied in completely different contexts too.

### What is the difference between classification and status?
The **classification** describes what the entry *is* (decision, proposal, assumption, rejected alternative, open question or lesson). The **status** describes a decision's *life cycle* (proposed, active, superseded, rejected or paused). A proposal therefore cannot have the status `Active` — only decisions have a life-cycle status.

### Must every decision have a reusable lesson?
No. Some decisions are entirely specific to the moment. In that case, write **No reusable lesson identified**.

### May I paste text from the source documents into the log?
No, as a rule not. **Refer, don't recreate.** If you paste in longer excerpts, you create a duplicate that can go stale when the source is updated — and then no one knows which one applies. Instead, refer by file name and version under Source material (e.g. "Requirements spec v1.2, section 4.2").
- **Exception:** What is required for the decision to be understood and revisited without the source should remain in the entry. Rule of thumb: *enough that the decision can be understood, little enough that it does not become a copy.*

### What about sensitive data?
It never belongs in a Dialogue Synthesis. The log is designed to travel between chats, agents and people — therefore it must not contain passwords, API keys, access tokens or personal data. Remove such content before the log is saved; any need for sensitive data in the dialogue is handled in the dialogue, not in the memory.

### Why does it say "Not documented" as the decision date?
Decisions in dialogues are rarely made at an exact moment — they often mature over several messages. A guessed exact date gives false precision and false authority; "Not documented" is more honest. Therefore:
- State an exact day only if it is evident from the dialogue.
- Otherwise month precision (YYYY-MM) is enough — the agent can often infer the month.
- The document's *Last updated* (in the document frame) is always exact and is the primary date.
- The chronology is often clearer from the chaining (supersedes/superseded by) than from dates.

*Tip for better precision — entirely optional:* write today's date in the chat when a session starts, and check the platform's timestamps when the synthesis is created. Neither is a requirement.

### What happens if a decision changes in a future chat?
1. Do not change the original text in the history.
2. Create a new decision entry (e.g. `BL-005`).
3. Mark the old decision as `Superseded` and link to the new one via **Superseded by / Supersedes**.

---

## 6. Tips for advanced users

### Use tags for better searchability
Use consistent tags (e.g. `tags: AI, architecture, cost`) in the header section to make it easy to filter decisions in larger repositories.

### Compile a central lesson registry
When several projects generate similar lessons, collect them in a shared registry.

| Lesson ID | Reusable lesson | Originating decisions | Relevant contexts | Status |
|---|---|---|---|---|
| L-001 | [Lesson] | [BL-001, BL-003] | [Project/Context] | [Established / Preliminary] |

Recurring lessons can later be developed into:
- Company-specific system prompts
- Method rules and quality criteria
- `.cursorrules` files or instructions to code agents

---

## 7. Checklists

### Review checklist (AI proposes, a human approves)
- [ ] The decision text is understandable entirely without access to the original chat.
- [ ] It is clear which Work Product the decisions are linked to.
- [ ] The status is correctly stated (according to the template's status values).
- [ ] Assumptions and uncertainties are separated from the decision.
- [ ] Reusable lessons do not merely repeat the decision, but give a general principle.
- [ ] Source material is referred to by version or identifier — not copied.
- [ ] The log contains no passwords, API keys or personal data.

---

## 8. Templates & prompts

### Standard Prompt 1: Create/Update Dialogue Synthesis (Chat 1)
> *"Analyse our dialogue and create a Dialogue Synthesis based on the Dialogue Synthesis Template (v1.0). Identify significant decisions and link them clearly to our produced work product. Strictly distinguish between decisions, proposals, assumptions, rejected alternatives, open questions and reusable lessons, and give each decision a status (Proposed, Active, Superseded, Rejected or Paused). Refer to source material by file name and version instead of copying it in, and do not include passwords, API keys or personal data. Do not guess anything that is not evident. Formulate every decision so that it can be understood without access to the original dialogue."*

### The Ingestion Prompt (Chat 2) — see separate file
The prompt for loading the context into a new chat is available as its **own, canonical file in the package**: `dialogue-synthesis-ingestion-prompt-v1-0.md` (version 1.0). Paste it into Chat 2 together with today's goal, at the same time as the Work Product and the Dialogue Synthesis are uploaded.

The text is not reproduced here — according to the model's own rule: **refer, don't recreate**. Always follow the file if it is updated; it is the source.

---

## 9. Summary: Key principles

1. **Document decisions, not the entire dialogue.**
2. **Always let the Work Product and the Dialogue Synthesis travel together.**
3. **Keep the decision entry self-contained and understandable without the chat log.**
4. **Distinguish decisions from proposals, assumptions and open questions — and classification from status.**
5. **Let AI propose and a human review.**
6. **Separate the reusable lesson from the specific decision.**
7. **Generalise lessons with care.**
8. **Refer, don't recreate — cite source material with a version.**
9. **Keep sensitive data out of the log.**

---

## 10. Next steps

- Choose a finished dialogue and create your first Dialogue Synthesis.
- Test starting Chat 2 by uploading *both* your work product and the synthesis, and pasting in the Ingestion Prompt.
- Evaluate whether the new AI agent maintains the stringency and respects your decisions.

**Good luck!**