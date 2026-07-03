---
name: frebuff-conductor-implement
description: Выполняет задачи из plan.md активного трека по порядку: TDD, реализация, верификация, коммит. Используй когда трек спланирован и готов к реализации.
---

# frebuff-conductor-implement

Последовательное выполнение задач трека по плану из `plan.md`.

## When to use

- После создания трека через frebuff-conductor-new-track
- Когда трек в статусе `pending` или `in_progress`
- Для продолжения прерванной реализации

## Instructions

### Step 1: Выбери трек

Прочитай `conductor/tracks.md`. Выбери первый трек с `pending`/`in_progress`. Если все `completed` — «Все треки завершены!»

### Step 2: Загрузи контекст

Прочитай: `spec.md`, `plan.md`, `metadata.json`, `workflow.md`, `tech-stack.md`, `product-guidelines.md`.

### Step 3: Обнови статус

`metadata.json` → `"status": "in_progress"`

### Step 4: Выполняй задачи последовательно

Для каждой `[ ]` задачи:

**a)** Отметь `[~]` (in progress) в plan.md

**b)** TDD цикл (если workflow требует):
- RED: напиши тест → запусти → должен упасть
- GREEN: минимальная реализация → тест проходит
- REFACTOR: улучши код → тесты проходят

**c)** Обычные задачи:
- file-picker для поиска релевантных файлов
- read_files для чтения
- str_replace / write_file для изменений
- basher для запуска тестов/линтера

**d)** Quality Gate:
- `pytest tests/ -v` → все тесты проходят
- coverage ≥ 80%
- Без bare except, console.log, хардкода

**e)** Отметь `[x]` в plan.md

**f)** Верификация фазы: когда доходишь до `User Manual Verification` — спроси пользователя через ask_user, всё ли работает.

### Step 5: Завершение трека

Когда все задачи `[x]`:
1. Запусти code-reviewer-deepseek
2. `metadata.json` → `"status": "completed"`
3. Обнови `conductor/tracks.md`
4. Обнови `CHANGELOG.md` при необходимости

### Step 6: Очистка

Спроси: «Архивировать трек?» / «Оставить как есть?» / «Удалить?»

### Правила реализации

- Делай только то, что в задаче, не больше
- Следуй конвенциям соседнего кода
- Используй существующие хелперы, не изобретай заново
- Тест падает → чини код, а не тест
- Архитектурные решения → запиши в `decisions.md`
