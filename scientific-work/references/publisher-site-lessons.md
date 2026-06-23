# Publisher Site Lessons

Use this file for compact reusable lessons from publisher, DOI, repository, and literature-hosting sites. Keep entries practical: site, symptom, route, what worked, and what to avoid. Do not store credentials, cookies, session tokens, personal data, or one-off private state.

## General Rules

- Before downloading from a publisher page, search the vault for an existing PDF by DOI, DOI-safe fragment, DOI suffix, year, and stable title words. Existing filenames may contain truncated, corrected, translated, or slightly wrong titles.
- If an existing valid PDF is found, update the project manifest/checkpoint with the local path instead of creating a duplicate. Treat DOI and DOI-suffix matches as strong; treat title-only matches as candidates that need manual confirmation, especially for families of papers with similar PCM/plasmonics titles.
- If a publisher page blocks script-based PDF access with 403 or a bot/security check, do not immediately mark the paper unavailable. Try the in-app browser and, when needed, let the user complete institutional login or browser verification in the visible UI.
- When a new site-specific route is learned, append a short note here after the session.

## AIP Publishing

- `pubs.aip.org` may show a Cloudflare/security verification page before the real article page or institutional-login flow. Treat this as a browser-verification blocker, not as evidence that the university has no access.
- Direct AIP PDF URLs discovered through metadata can return HTTP 403 to shell downloaders even when the article page is reachable in a browser. Before spending time on browser login, run the duplicate-PDF check because older AIP papers may already exist in the vault under year-title filenames.

## Optica Publishing Group

- Optica pages often resolve to `opg.optica.org/.../abstract.cfm?uri=...`. Check the article page for PDF/View Media and institutional-login controls before marking a DOI unavailable.
- For Optica EIM/waveguide papers, keep the DOI and `uri` value in the checkpoint; page titles and metadata can be less stable than the DOI.
