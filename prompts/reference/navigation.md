# Навигация по проекту Val'trey

## Каталоги
Инструкции для AI и резюме работ с агентами:
```
I:\Мой диск\DND\.llm
```
Каталог хранилища Obsidian:
```
I:\Мой диск\DND\Obsidian\DnD.Valtray
```

## Два контекста путей

У тебя есть два набора инструментов для работы с файлами. Каждый требует свой формат пути:

### CLI-инструменты (Grep, Glob, Read, Edit)
Полный путь от рабочей директории:
```
I:\Мой диск\DND\Obsidian\DnD.Valtray\0.Лор\НПЦ\Common\Борг Пепельный.md
```

### MCP Obsidian (read_note, write_note, search_notes, list_notes)
Путь относительно корня MCP (`I:\Мой диск\DND\`):
```
Obsidian/DnD.Valtray/0.Лор/НПЦ/Common/Борг Пепельный.md
```

Сокращения для удобства:
- **VAULT** = `Obsidian/DnD.Valtray` (для MCP)
- **VAULT_ABS** = `I:\Мой диск\DND\Obsidian\DnD.Valtray` (для CLI)

---

## Метаданные (Frontmatter)

Все файлы содержат frontmatter с метаданными для плагина Obsidian Bases.

### Типовые поля

```yaml
type:         # Тип сущности (npc, location, organization, item, event, state, creature)
name:         # Имя (для удобства)
created:      # Дата создания (YYYY-MM-DD)
modified:     # Дата последнего изменения
author:       # Кто создал (claude, gemini, chatgpt, user)
status:       # Статус (draft, reviewed, final, archived)

# Связи (только если применимо)
location:     # Где находится (wikilink: "[[Город]]")
organization: # Принадлежность (wikilink: "[[Организация]]")
race:         # Раса (для NPC)
ruler:        # Правитель (для государств)
parent:       # Родительская сущность (например: город → государство)

# Категории
tags:         # [категория1, категория2, роль]
```

### Пример для NPC

```yaml
---
type: npc
name: Борг Пепельный
race: минотавр
location: "[[Сейра]]"
organization: "[[Городская стража]]"
tags: [npc, страж, unique]
created: 2026-02-07
modified: 2026-02-07
author: claude
status: draft
---
```

---

## Поиск файлов

### Через CLI (Grep / Glob)

Всегда используй полный путь. Уточняй подпапку и категорию вместо поиска по всему Vault.

```bash
# Найти файл о конкретном городе
Glob: pattern="**/*Сейра*.md" path="I:\Мой диск\DND\Obsidian\DnD.Valtray\0.Лор\Мир\Атлас"

# Найти NPC по имени
Glob: pattern="**/*Борг*.md" path="I:\Мой диск\DND\Obsidian\DnD.Valtray\0.Лор\НПЦ"

# Найти легендарных NPC
Glob: pattern="**/*.md" path="I:\Мой диск\DND\Obsidian\DnD.Valtray\0.Лор\НПЦ\Legendary"

# Найти всех NPC в Сейре (по frontmatter)
Grep: pattern="location:.*Сейра" path="I:\Мой диск\DND\Obsidian\DnD.Valtray\0.Лор\НПЦ"

# Найти членов организации
Grep: pattern="organization:.*Железная воля" path="I:\Мой диск\DND\Obsidian\DnD.Valtray\0.Лор\НПЦ"

# Найти по тегам
Grep: pattern="tags:.*страж" path="I:\Мой диск\DND\Obsidian\DnD.Valtray\0.Лор\НПЦ"

# Найти по типу
Grep: pattern="type: location" path="I:\Мой диск\DND\Obsidian\DnD.Valtray\0.Лор\Мир\Атлас"

# Найти по расе
Grep: pattern="race: минотавр" path="I:\Мой диск\DND\Obsidian\DnD.Valtray\0.Лор\НПЦ"

# Найти информацию о конкретной расе
Grep: pattern="Аквелиры" path="I:\Мой диск\DND\Obsidian\DnD.Valtray\0.Лор\Мир\Расы"
```

### Через MCP Obsidian

```bash
# Поиск по содержимому (все заметки)
search_notes: query="Сейра"

# Список заметок в конкретной папке
list_notes: folder="Obsidian/DnD.Valtray/0.Лор/НПЦ/Common"

# Чтение конкретной заметки
read_note: path="Obsidian/DnD.Valtray/0.Лор/НПЦ/Common/Борг Пепельный.md"

# Структура папки
list_directories: folder="Obsidian/DnD.Valtray/0.Лор/Мир"
```

---

## Wikilinks и связи

При создании/редактировании файлов создавай wikilinks для связности:
- `[[Организация]]` — если сущность член организации
- `[[Локация]]` — где базируется/происходит
- `[[Раса]]` — для NPC
- `[[Событие]]` — для связи с историческими событиями

Дублируй ключевые связи в frontmatter — это нужно для плагина Obsidian Bases, который строит базы данных по метаданным:

```yaml
location: "[[Сейра]]"
organization: "[[Гильдия Воров]]"
tags: [npc, вор, человек]
```
