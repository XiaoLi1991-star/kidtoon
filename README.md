# KidToon

KidToon is a Codex skill for querying and maintaining a parent-facing kids cartoon episode database in Markdown.

It is designed for questions like:

- Which platform has this season or episode?
- What is the Tencent Video title or episode number?
- Which episodes include a character?
- Is an answer sourced from the local Markdown database or inferred?

The packaged skill uses three query Markdown files per cartoon:

- `01-分集平台清单.md`
- `02-分集人物索引.md`
- `03-平台标题映射-腾讯视频.md`

Development-only research notes are kept out of the published skill unless they are explicitly needed.

This repository includes the Codex skill instructions and the current bundled Markdown database for:

- 汪汪队立大功
- 奇妙萌可

## Install

Install the skill folder `kidtoon` into Codex skills, then restart Codex to pick it up.
