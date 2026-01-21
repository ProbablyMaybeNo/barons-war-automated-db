# AI Integration Index

This directory provides **AI-friendly discovery artifacts** that normalize how chat systems locate rules content across modules.

## Contents

- `catalog.json` lists every module and points to its section index.
- `section-index/*.json` maps human-friendly titles to JSON Pointers inside each `rules.json`.
- `section-templates.json` defines canonical section labels for consistent retrieval across multiple repos.
- `schema/*.schema.json` provides JSON Schema definitions for validation.

## How to Use (Example)

1. Load `ai/catalog.json` to enumerate modules.
2. For a user request like "show me the campaign rules", pick the module and read its `section-index` file.
3. Find a section whose `title` or `id` matches the query (e.g., `campaign_rules`).
4. Use the `json_pointer` to extract data from the module's `rules.json`.

This makes it easy for chat-based systems to map human queries to structured data without needing to parse PDFs.
