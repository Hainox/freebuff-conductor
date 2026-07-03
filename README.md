# Freebuff Conductor

> Codebuff-скиллы для Context-Driven Development. Аналог [claude-conductor](https://github.com/rbarcante/claude-conductor), адаптированный под Codebuff.

## Скиллы

| Скилл | Назначение |
|-------|------------|
| `freebuff-conductor-setup` | Инициализация проекта, создание `conductor/` |
| `freebuff-conductor-new-track` | Создание трека (spec + plan) |
| `freebuff-conductor-implement` | Выполнение задач трека по TDD |
| `freebuff-conductor-status` | Статус проекта и всех треков |

## Установка

```bash
npx skills add Hainox/freebuff-conductor
```

## Использование

После установки скиллы доступны через `/` в Codebuff CLI:

```
/freebuff-conductor-setup     — инициализация проекта
/freebuff-conductor-new-track — новый трек
/freebuff-conductor-implement — выполнение трека
/freebuff-conductor-status    — статус проекта
```
