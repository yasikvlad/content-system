---
description: Полный контент-конвейер из исходного материала → Notion
allowed-tools: Read, Write, Edit, Bash, Grep, Glob, Task, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-create-pages, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-update-page, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-fetch, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-search, mcp__dff121fa-9087-4ed6-a5cd-ad057b2d3589__notion-query-data-sources
argument-hint: [вставь текст, транскрипцию или статью]
---

## ОБЯЗАТЕЛЬНЫЙ ШАГ 1 — загрузи все инструкции

Прочитай ВСЕ следующие файлы через Read tool ДО начала любой генерации:

1. `${CLAUDE_PLUGIN_ROOT}/skills/content-pipeline/SKILL.md` — логика конвейера, анализ, форматы, Notion-конфиг
2. `${CLAUDE_PLUGIN_ROOT}/skills/reels-creator/SKILL.md` — форматы и правила для Reels
3. `${CLAUDE_PLUGIN_ROOT}/skills/reels-creator/references/примеры_вирусных_рилс.md` — референсы для Reels
4. `${CLAUDE_PLUGIN_ROOT}/skills/short-post-creator/SKILL.md` — правила и референсы для коротких постов
5. `${CLAUDE_PLUGIN_ROOT}/skills/long-post-creator/SKILL.md` — паттерны и принципы для длинных постов
6. `${CLAUDE_PLUGIN_ROOT}/skills/carousel-post-creator/SKILL.md` — типы и структура каруселей
7. `${CLAUDE_PLUGIN_ROOT}/skills/article-creator/SKILL.md` — жанры, принципы и разборы для статей

Без этого шага качество генерации будет низким. Прочитай все файлы, прежде чем переходить дальше.

---

## ШАГ 2 — запусти конвейер

Обработай материал пользователя ($ARGUMENTS или из чата) согласно инструкциям из content-pipeline SKILL.md:

1. Создай запись-исходник в Notion «Исходники» (data_source_id: `30eb40e2-0a6e-8051-aef1-000b33fa8801`)
2. Проанализируй материал → выдели золотые куски (триггерные моменты с вирусным потенциалом)
3. Для каждого подходящего куска сгенерируй форматы согласно загруженным SKILL.md:
   - **Reels** — по reels-creator SKILL.md (форматы, хуки, байты)
   - **Карусель** — по carousel-post-creator SKILL.md (тип карусели, слайды, текст под постом)
   - **Короткий пост** — по short-post-creator SKILL.md (стиль референсов)
   - **Длинный пост** — по long-post-creator SKILL.md (паттерн + 12 принципов)
   - **Статья** — по article-creator SKILL.md (жанр + принципы)
4. Каждую единицу контента сохрани как отдельную страницу в Notion

**Язык по умолчанию:** русский → «🇷🇺 Контент RU» (data_source_id: `769dab3e-8928-4f6c-ae85-a70044df0c28`)
**На английском:** → «🇬🇧 Content EN» (data_source_id: `a5efc439-51a0-4692-a999-6968ac538e82`)

**Режимы:**
- «только анализ» / «золотые куски» → только этап анализа, покажи куски и жди
- «только рилсы» / «только карусели» / «только пост» → генерируй только нужный формат
- Без уточнений → полный автомат, генерируй всё

**Правила:**
- Факты ТОЛЬКО из исходника — ничего не выдумывать
- Полный текст контента — в body страницы Notion, НЕ в свойствах
- Свойства — только для тегирования и фильтрации
