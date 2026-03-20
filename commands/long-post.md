---
description: Генерация длинного поста (2000-3000 знаков) из исходного материала → Notion
allowed-tools: Read, Write, Edit, Bash, Grep, Glob, Task, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-create-pages, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-update-page, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-fetch, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-search, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-query-data-sources
argument-hint: [вставь текст, тему или исходный материал]
---

Read the skill file at `${CLAUDE_PLUGIN_ROOT}/skills/long-post-creator/SKILL.md` — it contains 5 structural patterns, 12 principles of live writing, platform adaptation, and a quality checklist.

Analyze the user's input (provided as $ARGUMENTS or in the conversation). Extract the key insight, story, or mechanism.

**Step 1 — Choose pattern:**
Determine the most fitting structural pattern:
1. История с трансформацией — if there's a personal story or case with a before/after
2. Механика / Что я делаю по-другому — if the material is about a specific approach or system
3. Разрушение стереотипа — if there's a counterintuitive claim to make
4. Итоги / Рефлексия — if summarizing a period or project
5. Наблюдение за трендом — if commenting on an industry shift

If the user specifies a pattern, use it. If not, choose and explain.

**Step 2 — Write the post:**
Apply the chosen pattern structure from the skill file. Target 2000-3000 characters. Embed the 12 live writing principles throughout. Read aloud test: every sentence that sounds robotic — rewrite.

**Step 3 — Save to Notion:**
Save as a page:

**For Russian (default):** «🇷🇺 Контент RU» (data_source_id: 769dab3e-8928-4f6c-ae85-a70044df0c28)
**For English:** «🇬🇧 Content EN» (data_source_id: a5efc439-51a0-4692-a999-6968ac538e82)

Page properties:
- Название/Name: «Пост: [краткое описание]»
- Формат/Format: Пост / Post
- Статус/Status: Черновик / Draft
- Тема/Topic: determine from content
- Заметки/Notes: «длинный» / «long»
- Исходник/Source: URL of the source page (if exists)

Full post text goes into page CONTENT (body), not properties.

Rules:
- Facts ONLY from source — never invent
- Russian by default, живой разговорный тон
- No канцеляризмы — check against the banned words list in the skill
- Apply quality checklist before finalizing
- Generate 1-2 post variants if the material allows multiple angles
