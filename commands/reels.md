---
description: Быстрая генерация вирусных Reels из текста → Notion
allowed-tools: Read, Write, Edit, Bash, Grep, Glob, Task, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-create-pages, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-update-page, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-fetch, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-search, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-query-data-sources
argument-hint: [вставь текст поста или транскрипции]
---

Read the skill file at `${CLAUDE_PLUGIN_ROOT}/skills/reels-creator/SKILL.md` — it contains all 10 viral formats with embedded reference examples, hook patterns, script formula, bait system for Telegram, and Notion integration config.

Analyze the user's input text (provided as $ARGUMENTS or in the conversation). Extract key facts, tools, stories, audience pains.

Generate exactly 6 Reels scripts — a mix of durations for A/B testing:

**4 SHORT scripts (15-25 sec each):**
- Minimal text (4-6 sentences per script)
- Format: title + full script text + visual notes (2-3 bullets) + bait
- No second-by-second breakdowns

**2 LONG scripts (45-60 sec each):**
- Detailed second-by-second breakdowns (5-7 sec chunks)
- Full structure: HOOK → PROBLEM → SOLUTION → BAIT + CTA
- Include video description text

Each script is saved as a SEPARATE page in Notion:

**For Russian (default):** «🇷🇺 Контент RU» (data_source_id: 769dab3e-8928-4f6c-ae85-a70044df0c28)
**For English:** «🇬🇧 Content EN» (data_source_id: a5efc439-51a0-4692-a999-6968ac538e82)

For each Reels page, set properties:
- Название/Name: «Reels: [краткое описание]»
- Формат/Format: Reels
- Статус/Status: Черновик / Draft
- Тема/Topic: determine from content
- Хронометраж/Duration: match script length
- Вирусный формат/Viral format: which format from the database was used
- Кодовое слово/Code word: the Telegram bait word
- Исходник/Source: URL of the source page (if exists)

Full script text goes into page CONTENT (body), not properties.

Rules:
- Facts ONLY from the source material — never invent
- Russian language by default, casual tone, на «ты»
- Each script = one viral format (don't mix)
- Use REFERENCE EXAMPLES from the skill as style guides
- Each bait must be unique and specific
