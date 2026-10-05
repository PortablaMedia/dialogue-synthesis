# Ingestion Prompt — Dialogue Synthesis

**Version:** 1.0 — part of the Dialogue Synthesis package v1.0  
**Use:** Paste the text below at the start of a new chat (Chat 2), while the work product and the Dialogue Synthesis are uploaded. This file is the **canonical** ingestion prompt — the User Guide refers here and does not reproduce the text (rule: *refer, don't recreate*).

---

```text
We are continuing our work. I am uploading documents from our previous work: (1) our latest work product [filename] and (2) our Dialogue Synthesis [filename]. Read through the documents and act according to the following rules of play:

1. Active decisions: Treat all decisions marked as Active as locked frames. Do not revisit or challenge them unless I explicitly ask you to.
2. Assumptions: Note the documented Assumptions. If our new work touches them, help me validate them instead of assuming they are fact-based.
3. Reusable lessons: Apply relevant lessons as guiding principles in our continued work.
4. Stringency: Build on the resolution and level of detail present in the work product. Do not generate bloated or sweeping lists — keep the suggestions as concrete as in the previous step.

Focus: Our goal in this session is to [briefly describe what is to be done and why]. Pay particular attention to the documented Open questions.

Confirm briefly that you have understood the context and the active decisions, and tell me how we best approach today's goal. Let me know if anything is missing or unclear.
```