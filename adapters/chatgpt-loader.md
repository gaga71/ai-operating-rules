# ChatGPT Custom Instructions Loader

Use this file as the short loader copied into ChatGPT Custom Instructions when the full ordinary-execution adapter is too large for the UI field.

This loader does not replace `adapters/chatgpt.md`. The full deployment rules remain in that file, and the canonical maintenance source remains under `rules/`, `domains/`, `quality/`, and `governance/`.

## Custom Instructions text

AI operating rules are maintained outside Custom Instructions because the UI field may be too small for the full deployment artifact.

For ordinary execution, when file search or file access is available, use the newest accessible file whose name matches `AI_OPERATING_RULES_YYYY-MM-DD_<main-short-sha>.md` from the current chat, project, or Library. Treat that file as the ordinary-execution deployment copy derived from `gaga71/ai-operating-rules` `main` / `adapters/chatgpt.md`.

Do not rely on remembered, summarized, or older copies when a newer deployment file has actually been loaded. If multiple candidate files are accessible, use the newest unambiguous one by filename date and available file metadata. If the newest file cannot be determined, do not guess.

Do not retrieve the GitHub repository solely to compare versions during ordinary execution. If no current deployment file is accessible, do not claim that the external operating rules were applied; continue under the current explicit instructions and higher-level ChatGPT instructions. When exact rule wording, rule-system maintenance, or repository updates are requested, retrieve the canonical repository and follow its `README.md` loading path.

The repository defines rule content; this loader only defines how to locate the deployment copy. Current explicit instructions and higher-priority instructions still take precedence over repository rules.

## Usage notes

- ChatGPT Custom Instructions have a product-defined character limit, so keep this loader short rather than copying the full deployment adapter into the UI.
- Files uploaded to or created in ChatGPT may be stored in Library and reused across chats, but automatic retrieval is not guaranteed in every surface or workspace configuration. If reliable application matters and the file was not retrieved automatically, explicitly attach or select the latest deployment file from Library.
- Project instructions can override global Custom Instructions. If a project must use the same loader reliably, put an equivalent loader in that project's instructions or add the current deployment file to the project context.
- Do not use this loader as the source for rule-system maintenance.