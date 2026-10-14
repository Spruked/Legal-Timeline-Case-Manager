# Legal Timeline Case Manager — Fresh Start

This is a clean new project, not a revision of the earlier Missouri organizer. It has **no preloaded cases, notes, legal judgments, or imported personal documents**.

## Goal
A document-driven legal case manager. Drop documents into a case, extract their dates/events/places/people, place dated events on a **real horizontal timeline**, and let the user edit everything. Capture **what, when, where, who, source** without legal interpretation.

## Quick start
Open `index.html` in a modern desktop browser. It is a standalone, dependency-free **UI foundation**, with a functioning horizontal timeline, manual event editor, document drag/drop and persistent local browser storage. PDF/OCR and automatic document-to-event extraction are **not yet implemented**: see `CODEX_TASK.md`.

## Handoff to Codex
1. Open this folder in Codex.
2. Give Codex `CODEX_TASK.md` as its implementation instructions.
3. Preserve user-controlled edits and originals. Build automatic document parsing incrementally with visible browser tests.

## Key rules
- A document date and the date(s) of events described in the document are different fields.
- One source can support multiple events; one event can link to multiple sources.
- Keep extracted source text separate from user-edited timeline entries.
- Dates that are uncertain must not be silently invented.
- The app records and organizes, **never determines legal outcome or requirements**.
- All imported files and case records stay user-owned; provide a complete export/import with originals.

## License and privacy

**Proprietary — all rights reserved.** Original Legal Timeline Case Manager materials are governed by the root [LICENSE](LICENSE). Bundled dependencies and separately licensed works keep their own licenses; see [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

This is a general-purpose legal records organizer, not a repository of any individual's court history. Do not commit real case files, imported documents, sensitive records, or credentials. Repository visibility is currently public; changing visibility is a separate GitHub setting.
