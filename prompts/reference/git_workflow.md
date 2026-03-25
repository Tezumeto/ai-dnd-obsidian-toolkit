# Git Workflow для .llm/

AI-инструкции `.llm/` находятся под контролем версий Git.

## Когда создавать коммиты

- После значимых изменений в `prompts/` или `skills/`
- После создания/обновления skills
- При финализации резюме сессии (если были изменения в инструкциях)

## НЕ коммитить автоматически

- Изменения в `summary/` (исключены в .gitignore)
- Изменения в `log/` (исключены в .gitignore)
- Временные файлы

## Формат коммит-сообщения

```
<тип>: <краткое описание>

<детали изменений, если нужно>

Co-Authored-By: <Агент> <email>
```

### Типы коммитов

- `feat:` — новый skill или функционал
- `update:` — обновление существующего файла
- `fix:` — исправление ошибки в инструкциях
- `refactor:` — реструктуризация без изменения функционала
- `docs:` — изменения в README или документации

### Примеры

```bash
# Добавление нового skill
git commit -m "feat: add encounter_design skill

- Structure for combat/social/exploration encounters
- Balance guidelines for CR calculation
- Examples for different party levels

Co-Authored-By: Claude Opus 4.6 <noreply@anthropic.com>"

# Обновление system.md
git commit -m "update: add Git workflow section to system.md

Co-Authored-By: Claude Opus 4.6 <noreply@anthropic.com>"
```

## Workflow

1. Внёс изменения в файлы `.llm/prompts/` или `.llm/skills/`
2. Проверь статус: `git status`
3. Добавь изменения: `git add <файлы>`
4. Создай коммит с осмысленным сообщением
5. Продолжай работу

## Запреты

- `git push` — нет удалённого репозитория
- `git branch` / `git checkout` — работаем только в main
- `git rebase` / `git reset --hard` — деструктивные операции
