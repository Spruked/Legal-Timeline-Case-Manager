# Codex implementation assignment — Legal Timeline Case Manager

## Mission
Complete this fresh-start, document-driven **legal case manager**. The main screen is a horizontally scrollable, zoomable chronological timeline, not a list. Users drop PDF/image/text documents, the app extracts date-bearing facts, and users can see and edit every event directly. This is a factual record-organizing tool, not a legal-analysis tool.

## Inspect existing foundation
Read README.md and inspect index.html, app.js, styles.css. Run it in a browser and inspect the console. There are no user files or preloaded case facts. Preserve the simple UI, working manual timeline, and user editing while extending capability.

## Data model
- Case: id, name, createdAt, editable lanes, events, documents.
- Document: id, original filename, mime type, bytes, import timestamp, document dates, extracted text, parser provenance/status.
- Event: id, title, startDate, optional endDate, date precision, description, location, county, state, organization/court, people, laneId, linked document IDs, source snippets/locations, manually edited values.
- Distinguish document issue date, file metadata date, event occurrence date, and date mentioned in a document.
- Multiple events per document, multiple documents per event.
- Record missing dates as unknown rather than placing them on today's date.

## Implementation milestones
1. **Validate foundation**: Run app and capture screenshot showing a horizontal date axis with lane markers, manual add/edit/delete and drag/drop. Fix issues and add browser tests.
2. **Document ingest**: Persist originals locally reliably (IndexedDB preferred), create/select/remove cases, import multiple PDFs, JPG/PNG, and TXT; preview originals; complete portable case export/import with files. Avoid loading entire large documents into localStorage.
3. **Extract text**: Parse text PDFs and TXT; OCR scanned PDFs and images, preferably using local/on-device options; show per-file parsing status and raw extracted text. Make fallback/manual entry possible without OCR.
4. **Extract event facts**: Detect dates, names, locations, court/organization, and short neutral event descriptions from text. Distinguish document date from occurrence date; use each date's immediate source context; support multiple facts/events; link to page/region when practical. No fabricated events/locations.
5. **Place visually**: Sort events and position markers/bars by parsed dates; allow unknown-date items in an unplaced tray; click events to edit all fields and view associated source; zoom decade/year/month/day; scroll; custom lanes; overlapping event layout.
6. **Usability & resilience**: Undo/redo, search, filtering, bulk selection, keyboard accessibility, export/import, autosave, error recovery, tests.

## Behavioral boundaries
- Record WHAT, WHEN, WHERE, WHO and SOURCE only. No adjudication, legal significance, compliance assessments, requirements advice, or confidence traffic lights.
- Extract suggestions are editable by the user and never silently overwrite manual edits.
- Do not add example 'facts' about the user's Missouri case.
- Keep records local unless the user explicitly configures a service. Avoid remote uploads by default.
- Keep original imported bytes intact and traceable to source entries.

## Test acceptance criteria
- On launch a horizontal dated timeline is plainly visible.
- Import 3 synthetic files with mixed dates (including a document dated after its described event): correct occurrence dates are used for timeline placement while document dates remain separately visible.
- A document with 2 dated events creates 2 separately editable events referencing one original file.
- An undated document is not arbitrarily pinned to an invented date.
- Change a date, see marker move; reload and confirm edits persist.
- Export a case and reimport it into a clean browser profile and confirm documents and events remain intact.
- Verify in an actual browser with screenshot and console clean; report tests and unimplemented features truthfully.

## Work protocol
Inspect -> implement one bounded milestone -> run tests -> capture evidence -> report. Keep functionality usable at each milestone.
