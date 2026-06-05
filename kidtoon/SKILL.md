---
name: kidtoon
description: Find, verify, and update kids cartoon episode Markdown databases, including bundled PAW Patrol and Catch! Teenieping data. Use when asked about streaming platforms, episode titles, Tencent mappings, summaries, character appearances, first appearances, aliases, or adding new cartoons to the KidToon MD structure.
---

# KidToon

## Data Root

Use the bundled database at `references\动画片小助手` by default.

If the user is working in the original local project, prefer the fresher workspace database at `D:\develop\工具开源\动画片小助手` when it exists. Otherwise use the bundled references.

If neither path is obvious, search the current workspace for `动画片小助手\README.md` or a cartoon directory containing:

- `01-分集平台清单.md`
- `02-分集人物索引.md`
- `03-平台标题映射-腾讯视频.md`

## Source Order

Read the database before answering whenever local files exist.

- Use `01-分集平台清单.md` for seasons, episode titles, summaries, keywords, and platform availability.
- Use `02-分集人物索引.md` for character, pet, monster, or role appearances.
- Use `03-平台标题映射-腾讯视频.md` for Tencent episode numbers, Tencent titles, and play URLs.

State the provenance in the answer. Say whether the result comes from a specific MD file, an official platform source recorded in the MD, Fandom/API data recorded in the MD, Bilibili as a non-official supplement, or explicit inference.

## Lookup Workflow

1. Identify the cartoon. If the title is ambiguous, ask one short clarifying question.
2. Search the relevant cartoon directory with `rg` first.
3. For character queries, search both Chinese and English aliases when known.
4. For first appearances, distinguish cameo/minor appearance from major/full debut.
5. For Tencent questions, verify against `03-平台标题映射-腾讯视频.md`; do not assume Tencent episode order equals the general episode list.
6. Answer concisely with season/part, episode number, title, role status if available, and source file.

## Update Workflow

When adding or revising a cartoon, keep the runtime bundle to these three query files:

- `01-分集平台清单.md`: main parent-facing index.
- `02-分集人物索引.md`: character appearance index.
- `03-平台标题映射-腾讯视频.md`: Tencent-specific title and episode mapping.

Keep development-only research notes outside the packaged skill unless the user explicitly asks to publish them.

Prefer official Chinese streaming pages for platform availability and platform titles. Use authoritative episode guides or Fandom/API data for character sections when Chinese sources are incomplete. Treat Bilibili collections, clips, previews, and uploader playlists as non-official supplements unless the official complete album is verified.

## Quality Rules

- Do not answer from memory when the MD database can be checked.
- Do not present inferred aliases, inferred appearances, or unverified platform availability as fact.
- Keep Chinese names when verified; otherwise preserve `EnglishName` or `中文/EnglishName` and note the alias status.
- Preserve user corrections in the query files or in development notes outside the packaged skill.
- If a domestic release is excluded by user instruction, keep it excluded until a newer explicit correction is added.
