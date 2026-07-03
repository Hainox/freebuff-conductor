---
name: freebuff-conductor-new-track
description: Создаёт новый трек (feature/bugfix/refactor) с spec.md и plan.md в conductor/tracks/. Используй когда нужно запланировать новую фичу или исправление.
---

# freebuff-conductor-new-track

Создание нового трека по методологии Context-Driven Development: спецификация + план реализации.

## When to use

- Когда нужно запланировать новую фичу
- Для багфикса с чётким планом исправления
- Для рефакторинга с документированными шагами

## Instructions

### Step 1: Проверь setup

Прочитай `conductor/index.md`. Если `conductor/product.md` нет — скажи сначала запустить **freebuff-conductor-setup**.

### Step 2: Получи описание

Спроси пользователя (ask_user): «Опиши трек в 1-3 предложениях.» Определи тип:

| Ключевые слова | Тип |
|---------------|------|
| добавить, создать, фича | `feature` |
| исправить, баг, ошибка | `bugfix` |
| переписать, рефакторинг | `refactor` |
| документация, readme | `docs` |

### Step 3: Исследуй контекст

Прочитай: `conductor/product.md`, `conductor/tech-stack.md`, `conductor/workflow.md`, `conductor/product-guidelines.md`. Для brownfield — `conductor/docs/`.

### Step 4: Сгенерируй spec.md

Спроси 3-5 уточняющих вопросов (ask_user):

- **Feature:** Что должно работать? Какие компоненты? Есть ли UI?
- **Bugfix:** Как воспроизвести? Где именно баг?
- **Refactor:** Что переписываем? Почему? Риски?

Структура spec.md:
```markdown
# Spec: <track_id>
## Goal (одно предложение)
## Acceptance Criteria (чекбоксы)
## Functional Requirements
## Non-Functional Requirements
## Out of Scope
```

### Step 5: Сгенерируй plan.md

Фазы с задачами, каждая с `[ ]` маркером. Последняя задача фазы: `Task: Conductor - User Manual Verification '<Phase>'`.

### Step 6: Запиши артефакты

1. ID трека: `shortname_YYYYMMDD`
2. Создай `conductor/tracks/<track_id>/`
3. Запиши: `index.md`, `metadata.json`, `spec.md`, `plan.md`
4. Обнови `conductor/tracks.md`

### Step 7: Завершение

- Покажи ID трека, количество фаз и задач
- Предложи коммит: `git add conductor/tracks/<track_id>/ && git commit -m "feat(conductor): Create track '<description>'"`
- Спроси: «Начать реализацию?» → если да, загрузи **freebuff-conductor-implement**
