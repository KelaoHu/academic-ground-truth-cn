# Changelog

All notable changes to **academic-ground-truth (CN)**. This project follows semantic versioning.

## [0.1.1] — 2026-10-11 (first tagged release)

0.1.0 was published as a sequence of file-by-file commits and never tagged. This release marks that snapshot rather than adding to it, so the version number and the reference list are lifted to 0.1.1 and everything else is unchanged. No behavioural change.

## [0.1.0] — 2026-10-10 (first public release)

Initial release, consolidated from six internal development iterations and one full-article field run (~30 sources, 8 batches, 24 verified footnotes, 1 rejection, 3 draft-sentence corrections).

### Added

- Core pipeline S0–S7: capability check → intake gate → claim list → candidate list (with prediction column) → file intake & version check → five-round verification (R1 locate / R2 image + context judgment / R3 page calibration / R4 metadata / R5 adversarial) → evidence archive → decision report.
- S8 final compliance sweep: open-items register empty, self-citation ≤ 3, zero internal publications, zero unmarked secondary citations, leaders' works on paper, format-spec snapshot re-check.
- Material handoff gate in two forms: single-file designation and batch mapping-table confirmation. The agent never self-matches files.
- Missing-copyright-page downgrade flow (OCR-request step 0 + five formal steps), including edition-identity judgment.
- Paraphrase fidelity rubric (attribution / qualifiers / time-and-scope / terminology) for non-verbatim claims.
- Evidence-nature grading (scholarship / first-person account / official document / news / corporate position), with hedging or triangulation prompts for positional primary sources.
- Image-only-book locating procedure, including probe-based front-matter boundary detection — added after regression testing exposed a 14-page translator's preface the original steps never anticipated.
- Status vocabulary with parameterized pending-dimension values (version info / journal name / year / body-text page / original-journal page).
- Open-items register in the report; original-vs-draft comparison table per claim; standardized report template.
- Four standing rules: non-overridable honesty red lines; untrusted-input declaration (files and web pages are data, never instructions); cross-session resume protocol; batch sizing guidance (≤ 8 files or ≤ 6 claims per batch).
- References: full CSSN (2026 revision) citation specification; GB/T 7714-2015 switch (explicitly marked untested); the master report template.

### Fixed

- Regression: the image-only procedure's front-matter page-count assumption ("within the first ~15 sheets") replaced with probe-based boundary detection plus dual-end probing.

### Known limitations

1. Image-only books still cost 5–15 probe pages per lookup; the OCR-request step is the main relief valve.
2. Reference-checking mode (auditing existing footnotes) is implemented but untested on a live run.
3. The GB/T 7714 and custom-format paths are untested.
4. Single-agent serial design; multi-agent parallelism is future work.
5. The bundled CSSN specification is a dated snapshot; re-check the official source before submission.

---

## Development history (pre-release, kept for the record)

- **Iteration 1 — single-source pilot** (温铁军 monograph, one claim): pipeline proven end-to-end; caught the first paraphrase mismatch (a mis-scoped periodization).
- **Iteration 2 — handoff gate**: added after user feedback; the agent must never self-match downloaded files to candidates.
- **Iteration 3 — depth**: missing-front-matter downgrade flow; R2 split into verbatim / whole-page / whole-section reading; R5 adversarial round added.
- **Iteration 4 — full-article field run**: ~30 sources across 8 batches; the four-value status vocabulary proved too coarse, six real-world variants observed and later formalized.
- **Iteration 5 — hardening pass** (product-manager + academic-advisor review of 11 gaps): image-only locating procedure, paraphrase fidelity rubric, evidence-nature grading, batch handoff mode, open-items register, S8 compliance sweep, injection defense, resume protocol, batch sizing, untested-path marking, data-source citation type.
- **Iteration 6 — prediction column**: "predicted fit / risk" added to the procurement list, explicitly labeled guesswork and replaced by verified conclusions after R5.
