# Maintenance protocol

This repository is a curated bibliography, not an automatically generated search index. Each entry should remain traceable to an authoritative source.

## Update cadence

| Cadence | Maintainer action |
|---|---|
| On paper release | Add a preprint only when it explicitly studies coupled low-light and resolution degradation. |
| On acceptance | Replace the preprint label with the verified venue, pages, DOI, and official project/code link. |
| Monthly | Review open suggestions and broken links. |
| Quarterly | Search major CV/ML venues, arXiv, Crossref, and official GitHub repositories; update this file's curation date in the README. |

## Evidence hierarchy

1. Publisher, conference proceedings, DOI registry, author project page, or official university page.
2. The authors' public GitHub repository for code, data, and release status.
3. arXiv only when a peer-reviewed record is unavailable.

Do not infer a venue from a repository name or cite an unofficial reproduction as author code.

## Status vocabulary

- **Code** — a public author-maintained implementation is available.
- **Repository** — an author repository exists but does not yet provide a runnable implementation.
- **Announced** — the relevant code/weights are promised but not released.
- **—** — no author-maintained resource was located during curation.

## Link checks

The scheduled GitHub Action checks external links weekly. A link failure is a maintenance signal, not proof that a paper or code release no longer exists; confirm the replacement with an authoritative source before changing an entry.
