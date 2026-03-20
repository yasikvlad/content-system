---
description: Генерация качественных статей из исходного материала → Notion
allowed-tools: Read, Write, Edit, Bash, Grep, Glob, Task, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-create-pages, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-update-page, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-fetch, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-search, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-query-data-sources
argument-hint: [вставь текст, тему или исходный материал]
---

Read the skill file at `${CLAUDE_PLUGIN_ROOT}/skills/article-creator/SKILL.md` — it contains the full genre framework (4 genres), 12 universal principles, 3 editorial breakdowns as reference examples, and Notion integration config.

Analyze the user's input text (provided as $ARGUMENTS or in the conversation). Extract key insights, stories, arguments, facts.

**Step 1 — Choose genre:**
Determine the most appropriate genre based on the material and user's goal:
1. Практическое руководство — if the material is instructional, tool-based, step-by-step
2. Притча с раскрытием механики — if there's a story or metaphor that reveals a deeper truth
3. Философское эссе с тезисом — if the material challenges assumptions or reframes perspective
4. Практический консультационный текст — if the material is advice for a specific difficult situation

If the user specifies a genre, use that. If not, choose the most fitting one and explain the choice.

**Step 2 — Write the article:**
Apply the appropriate genre structure and quality criteria from the skill file. Embed the 12 universal principles throughout. Use the 3 editorial breakdowns as reference for what good looks like.

**Step 3 — Save to Notion:**
Save the article as a page in Notion:

**For Russian (default):** «🇷🇺 Контент RU» (data_source_id: 769dab3e-8928-4f6c-ae85-a70044df0c28)
**For English:** «🇬🇧 Content EN» (data_source_id: a5efc439-51a0-4692-a999-6968ac538e82)

Page properties:
- Название/Name: «Статья: [краткое описание]»
- Формат/Format: Статья / Article
- Статус/Status: Черновик / Draft
- Тема/Topic: determine from content
- Исходник/Source: URL of the source page (if exists)

Full article text goes into page CONTENT (body), not properties.

Rules:
- Facts ONLY from the source material — never invent
- Russian language by default
- Apply quality checklist from the skill before finalizing
- Each article = one genre (don't mix genres)
- Aim for 800-3000 words depending on genre and material depth
