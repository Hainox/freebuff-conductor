# Frebuff Conductor

> Codebuff-скиллы для Context-Driven Development. Аналог [claude-conductor](https://github.com/rbarcante/claude-conductor), адаптированный под Codebuff.

## Скиллы

| Скилл | Назначение |
|-------|------------|
| `frebuff-conductor-setup` | Инициализация проекта, создание `conductor/` |
| `frebuff-conductor-new-track` | Создание трека (spec + plan) |
| `frebuff-conductor-implement` | Выполнение задач трека по TDD |
| `frebuff-conductor-status` | Статус проекта и всех треков |

## Установка

```bash
npx skills add Hainox/frebuff-conductor
```

## Использование

После установки скиллы доступны через `/` в Codebuff CLI:

```
/frebuff-conductor-setup     — инициализация проекта
/frebuff-conductor-new-track — новый трек
/frebuff-conductor-implement — выполнение трека
/frebuff-conductor-status    — статус проекта
```
