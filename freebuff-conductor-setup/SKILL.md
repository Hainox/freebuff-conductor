---
name: freebuff-conductor-setup
description: Инициализирует проект с conductor/ директорией: product.md, tech-stack.md, workflow.md, code_styleguides, tracks. Используй при первом запуске проекта или когда нужно настроить conductor-окружение.
---

# freebuff-conductor-setup

Инициализация проекта по методологии Context-Driven Development. Создаёт `conductor/` — единый источник правды для AI-агентов.

## When to use

- При первом запуске нового проекта
- Когда в проекте нет папки `conductor/`
- После клонирования проекта, где conductor ещё не настроен

## Instructions

### Step 1: Определи тип проекта

- **Brownfield:** есть `package.json`, `requirements.txt`, `go.mod`, `src/`, `app/`, `lib/`
- **Greenfield:** пустая папка или только `.git`

### Step 2: Собери контекст

**Greenfield:**
- Спроси пользователя через ask_user: «Что мы создаём? Опиши проект в 2-3 предложениях.»
- Спроси: «Какой основной язык/стек?»
- Спроси: «Нужны ли база данных, API, аутентификация?» (multiSelect)

**Brownfield:**
- Запусти file-picker и code-searcher для анализа кодовой базы
- Прочитай манифесты зависимостей
- Авто-определи стек, подтверди с пользователем

### Step 3: Создай структуру conductor/

```
conductor/
  index.md              # навигационный индекс
  product.md            # продукт: проблема, пользователи, функции
  product-guidelines.md # стиль, tone of voice, UI-правила
  tech-stack.md         # языки, фреймворки, инфраструктура, ADR
  workflow.md           # TDD, коммиты, quality gates
  tracks.md             # реестр треков
  setup_state.json      # состояние инициализации
  code_styleguides/     # гайды по стилю кода
  docs/                 # архитектура, нейминг, тестирование
  tracks/               # папка для треков (пустая)
```

### Step 4: Заполни файлы

- **product.md** — Vision, Problem, Users, Features, Non-Goals, Constraints
- **product-guidelines.md** — Brand, Colors, Typography, Quick Reference
- **tech-stack.md** — Languages, Frameworks, Infrastructure, ADR с датами
- **workflow.md** — TDD, commit format `type(scope): description`, coverage 80%+

### Step 5: Начальный трек

1. Создай первый трек в `conductor/tracks/initial_setup_YYYYMMDD/`
2. Файлы: `index.md`, `metadata.json`, `spec.md`, `plan.md`
3. 1-2 фазы с базовыми задачами
4. Зарегистрируй в `conductor/tracks.md`
5. `setup_state.json`: `{"last_successful_step": "3.3_initial_track_generated"}`

### Step 6: Завершение

- Выведи список созданных файлов
- Предложи: `git add conductor/ && git commit -m "chore(conductor): Initialize project context"`
- Сообщи: «Готово. Используй **freebuff-conductor:implement** для выполнения трека.»
