---
description: Быстрая генерация вирусных коротких постов из текста → Notion
allowed-tools: Read, Write, Edit, Bash, Grep, Glob, Task, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-create-pages, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-update-page, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-fetch, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-search, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-query-data-sources
argument-hint: [вставь текст, мысль или транскрипцию]
---

Read the skill file at `${CLAUDE_PLUGIN_ROOT}/skills/short-post-creator/SKILL.md` — it contains all 9 viral short post formats with embedded reference examples, style rules, and Notion integration config.

Analyze the user's input text (provided as $ARGUMENTS or in the conversation). Extract key insights, stories, provocative statements, concrete facts.

Generate 3-7 short posts (under 1000 characters each) — each in a different viral format:

**Formats available:**
1. Личная история / кейс
2. Инсайт-откровение
3. Контринтуитивная правда
4. Прозрачность решений
5. Философская рефлексия
6. Итоги / результаты
7. Провокационный тезис
8. Мудрость-панч
9. Наблюдение за рынком

Each post is saved as a SEPARATE page in Notion:

**For Russian (default):** «🇷🇺 Контент RU» (data_source_id: 769dab3e-8928-4f6c-ae85-a70044df0c28)
**For English:** «🇬🇧 Content EN» (data_source_id: a5efc439-51a0-4692-a999-6968ac538e82)

For each page, set properties:
- Название/Name: «Пост: [краткое описание]»
- Формат/Format: Пост / Post
- Статус/Status: Черновик / Draft
- Тема/Topic: determine from content
- Платформа/Platform: determine from context or ask
- Исходник/Source: URL of the source page (if exists)
- Заметки/Notes: «короткий» / «short»

Full post text goes into page CONTENT (body), not properties.

Rules:
- Facts ONLY from the source material — never invent
- Russian language by default, casual tone
- Each post = one format (don't mix)
- Use REFERENCE EXAMPLES from the skill as style guides
- Maximum 1000 characters per post, ideal 400-700
- Adapt to platform if specified (Threads, Instagram, Telegram, LinkedIn, Twitter)
