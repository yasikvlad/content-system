---
description: Генерация карусели для Instagram/LinkedIn из исходного материала → Notion
allowed-tools: Read, Write, Edit, Bash, Grep, Glob, Task, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-create-pages, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-update-page, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-fetch, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-search, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-query-data-sources
argument-hint: [вставь текст, тему или исходный материал]
---

Read the skill file at `${CLAUDE_PLUGIN_ROOT}/skills/carousel-post-creator/SKILL.md` — it contains 6 carousel types, anatomy of the ideal slide, post caption structure, and quality checklist.

Analyze the user's input (provided as $ARGUMENTS or in the conversation). Determine what the carousel should achieve.

**Step 1 — Choose carousel type:**
1. Пошаговая инструкция — if it's a how-to with clear steps
2. Список ошибок — if highlighting mistakes people make
3. Инсайт с доказательствами — if there's a counterintuitive claim to prove
4. До / После / Как — if there's a transformation story
5. Сравнение / VS — if comparing two approaches
6. История / Кейс — if there's a narrative to tell

If the user specifies a type, use it. If not, choose and explain.

**Step 2 — Write the carousel:**
- Create a cover slide headline (most important — stop-scroll)
- Write 6-9 content slides: one slide = one idea, max 4-5 lines per slide
- Write a final slide with specific CTA or question
- Write post caption: hook + «листай →» + question + hashtags

Apply the carousel principles from the skill file throughout.

**Step 3 — Save to Notion:**
Save as a page:

**For Russian (default):** «🇷🇺 Контент RU» (data_source_id: 769dab3e-8928-4f6c-ae85-a70044df0c28)
**For English:** «🇬🇧 Content EN» (data_source_id: a5efc439-51a0-4692-a999-6968ac538e82)

Page properties:
- Название/Name: «Карусель: [краткое описание]»
- Формат/Format: Карусель / Carousel
- Статус/Status: Черновик / Draft
- Тема/Topic: determine from content
- Платформа/Platform: Instagram
- Исходник/Source: URL of the source page (if exists)

Format in Notion content:
```
ОБЛОЖКА
[заголовок обложки]

СЛАЙД 1
Заголовок: [title]
[text]

СЛАЙД 2
Заголовок: [title]
[text]

...

ФИНАЛЬНЫЙ СЛАЙД
[CTA / question]

—————————————
ТЕКСТ ПОД ПОСТОМ:
[caption text]

ХЭШТЕГИ:
[hashtags]
```

Rules:
- Cover headline is the #1 priority — rewrite it until it stops scroll
- Each slide = one idea, never more
- Facts ONLY from source — never invent
- Russian by default
- Apply quality checklist before finalizing
