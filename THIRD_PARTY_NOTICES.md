# Third-party and separately licensed components

The repository-level `LICENSE` applies **only** to original Legal Timeline
Case Manager materials owned by Spruked. It does not relicense bundled works.

| Component | Directory | License / status |
| --- | --- | --- |
| Tesseract OCR | `tesseract/` | Apache License, Version 2.0; retain `tesseract/LICENSE`, applicable copyright notices, and other upstream notices. |
| A.I.M.S. | `AIMS/` | Separately licensed proprietary software under `AIMS/LICENSE`; inclusion here does not itself grant a customer a right to reuse or distribute it. |
| VisiData | `visidata/` (if present locally) | **Not yet verified in the GitHub snapshot.** Determine the upstream source/version and preserve its original license and notices before inclusion or redistribution. |

## Publication and distribution

- Do not place user documents, court records, evidence, local databases, credentials,
  or personal case data in source control.
- Before shipping installers, audit the full dependency tree, embedded fonts,
  OCR data/models, and license obligations of every distributed component.
- Bundled source does not mean a component is actually integrated into the app.
- Preserve the upstream copyright and license terms for each third-party work.
- Review the full tracked-file inventory and prior Git history for sensitive
  material; `.gitignore` only blocks *new, untracked* matching files.
