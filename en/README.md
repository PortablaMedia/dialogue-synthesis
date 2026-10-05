# Readme: The Dialogue Synthesis Package

**Package version:** 1.0  
*The Swedish version of the package is the authoritative source; this English version is a maintained translation.*

*This is the readme for the English language folder (`/en/`). Language selector, repository structure and the canon declaration are in the root readme: [`../README.md`](../README.md).*

## Package files

| File                                        | Role                                                            | Version |
|---------------------------------------------|-----------------------------------------------------------------|---------|
| `dialogue-synthesis-template-v1-0.md`       | **The model** — how the synthesis is built, classified, and maintained | 1.0 |
| `dialogue-synthesis-user-guide-v1-0.md`     | **The manual** — for humans                                     | 1.0     |
| `dialogue-synthesis-ingestion-prompt-v1-0.md` | **The ingestion prompt** — pasted into a new chat             | 1.0     |
| `Readme.md`                                 | **Package overview** and reading order                          | 1.0     |

*Dialogue Synthesis logs (e.g. `Dialogue_Synthesis_v1.md`) and any lesson registry are created per project and are not part of the package.*

---

## Frequently asked questions

**Which file is the Dialogue Synthesis model?**

> The Dialogue Synthesis Template.

**Which files should a new AI agent receive?**

*When the agent should **continue started work** (Chat 2):*
1. The work product (the substance)
2. The Dialogue Synthesis logs (the meta-context)
3. The ingestion prompt (pasted as text into the chat)
4. Any lesson registry
5. The template — if the agent needs to interpret classes and status values in depth, or if uncertainty arises

*When the agent should **create or update a Dialogue Synthesis:***
1. The template
2. The dialogue or work product the synthesis is to be built from

**Why must both documents always accompany a continuation?**

> Because the model and the decisions contain the actual thinking. But without the work product, the agent is forced to guess detail level and resolution — and the answers bloat. **The substance and the meta-context always travel together.**

**What is the manual for?**

> The manual mainly helps people use the model correctly.

---

## Changelog

**Package 1.0** — the first public version of the Dialogue Synthesis package: Template, User Guide, Ingestion Prompt, and Readme with a shared version.

*Internal development history (Decision Log v1 → the Dialogue Synthesis iterations up to 1.0) is kept separately and is not published.*