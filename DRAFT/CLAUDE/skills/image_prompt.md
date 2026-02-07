# Skill: Генерация промптов для изображений

## Когда использовать
- Пользователь просит создать промпт для изображения
- При создании NPC/локации упоминается "нужна картинка"
- Явный запрос "сгенерируй промпт для..."
- Массовая генерация промптов (серия персонажей, набор локаций)

---

## Контекст

**Целевые системы генерации:**
- Gemini 3 Pro (основная)
- DALL-E / Midjourney / Stable Diffusion (совместимые)

**Стиль сеттинга:** Dark fantasy, dnd art, digital art

---

## Формат промпта

### Для NPC (портреты)
```
[Раса] [пол], [профессия/роль], [ключевая деталь одежды/экипировки], [эмоция/выражение], [окружение если важно]
--ar 9:16, dnd art, digital art
```

### Для локаций
```
[Тип локации], [ключевые визуальные детали], [атмосфера/настроение], [время суток если важно], [масштаб: close-up / wide shot]
--ar 16:9, dnd art, digital art
```

### Для предметов
```
[Тип предмета], [материал], [магические эффекты если есть], [детали украшений], [фон: простой или контекстный]
--ar 1:1, dnd art, digital art, item art
```

### Для сцен / событий
```
[Описание действия], [количество персонажей], [окружение], [атмосфера], [динамика / статика]
--ar 16:9, dnd art, digital art, dynamic scene
```

---

## Обязательные элементы

### Для NPC:
1. ✅ **Раса и пол** (human male, dwarf female, tiefling non-binary)
2. ✅ **Основная роль** (city guard, tavern keeper, wizard, pirate)
3. ✅ **Ключевая деталь** (blue tabard, leather armor, golden staff, eyepatch)
4. ✅ **Эмоциональный тон** (stern, friendly, mysterious, menacing, weary)
5. ⚠️ **Окружение** (опционально, только если важно для контекста)

### Для локаций:
1. ✅ **Тип** (tavern, city square, dungeon entrance, throne room, harbor)
2. ✅ **Атмосфера** (gloomy, bustling, abandoned, majestic, mysterious)
3. ✅ **Ключевые детали** (2-3 визуальных элемента)
4. ⚠️ **Время суток** (опционально: dawn, dusk, night, midday)
5. ✅ **Масштаб** (wide shot для общего вида, detailed для крупного плана)

### Для предметов:
1. ✅ **Тип предмета** (sword, amulet, tome, potion)
2. ✅ **Материал** (steel, silver, leather-bound, crystal)
3. ⚠️ **Магические эффекты** (опционально: glowing runes, ethereal mist)
4. ✅ **Детали** (ornate handle, gemstone inlay, ancient inscriptions)
5. ✅ **Фон** (simple background / resting on pedestal / in character's hand)

---

## Особенности сеттинга Val'trey

При создании промптов учитывай:

### Тональность:
- **Dark fantasy** с элементами cosmic horror
- Мир жесток, но не безнадёжен
- Смешение рас и культур (особенно в портовых городах)
- Порты, торговля, мореплавание — частая тема

### Астральный Кит:
- Редко упоминается в обычных изображениях NPC/локаций
- Может быть частью космических/мистических сцен
- Используй для культовых артефактов или событий

### Эмблемы и символика:

**Города:**
- **Сейра:** серебряный якорь с золотой цепью
- **Другие:** уточни у пользователя при необходимости

**Организации:**
- **Королевство Фрия:** уточни при создании для Фрии
- **Другие:** проверяй в файлах организаций

### Расовое разнообразие:
Портовые города = мультикультурность. Варьируй расы:
- Люди, эльфы, дварфы (стандарт)
- Полуэльфы, полуорки, полурослики (смешение)
- Драконорождённые, тифлинги (экзотика)
- Гномы, гоблиноиды (редко, но возможно)

---

## Принципы написания

### ✅ Хорошо:
```
Half-elf female archer, wearing blue city guard tabard with silver anchor emblem, alert expression, standing on stone city wall at dusk, sea visible in background
--ar 9:16, dnd art, digital art
```

**Почему:**
- Чёткая раса и пол
- Профессия (archer) и организация (guard)
- Конкретная деталь (emblem)
- Эмоция (alert)
- Контекст (city wall, sea) создаёт атмосферу
- Правильное соотношение для портрета

### ❌ Плохо:
```
A guard
--ar 9:16
```

**Почему:**
- Слишком мало деталей
- Нет расы/пола
- Нет стиля
- Нет контекста
- Не ясна атмосфера

### ⚠️ Избегай:
- **Слишком длинные промпты** (>60 слов) — генератор может потеряться
- **Противоречивые детали** ("молодой древний эльф", "весёлый мрачный")
- **Анахронизмы** (огнестрельное оружие в стандартном D&D без уточнения)
- **Неоднозначность** ("красивый" vs "stern handsome features")

---

## Workflow

### Шаг 1: Определи тип изображения
- NPC (портрет)
- Локация
- Предмет
- Сцена/событие

### Шаг 2: Собери информацию

**Из файла NPC/локации (если создаётся вместе):**
- Раса, роль, внешность
- Организация (эмблемы, униформа)
- Локация (окружение)

**Из запроса пользователя:**
- Специфические пожелания
- Тон и атмосфера

### Шаг 3: Проверь эмблемы/символику
Если упоминается организация/город:
- Проверь файл организации: `!Лор/Мир/107_Организации/`
- Проверь файл города: `!Лор/Мир/103_Атлас/`
- Уточни у пользователя, если не найдено

### Шаг 4: Составь промпт
- Используй шаблон для типа изображения
- Добавь конкретные детали
- Проверь длину (30-60 слов оптимально)

### Шаг 5: Добавь в файл
**Секция в файле NPC/локации:**
```markdown
## Промпт для изображения
```
[Промпт здесь]
--ar 9:16, dnd art, digital art
```
```

**Или отдельный файл для серии:**
`!Черновик/prompts_[тема].md`

---

## Примеры по типам

### NPC: Стражник портового города
```
Human male city guard, wearing blue tabard with silver anchor-and-golden-chain emblem, leather armor underneath, stern expression, holding spear, standing at harbor gate, sea and ships visible in background
--ar 9:16, dnd art, digital art
```

### NPC: Таинственный торговец
```
Half-elf male merchant, wearing dark travel cloak with hood slightly back, sly smile, displaying exotic goods on portable stand, misty evening market atmosphere
--ar 9:16, dnd art, digital art
```

### NPC: Мистический персонаж
```
Tiefling female warlock, wearing dark robes with glowing purple runes, intense gaze, ethereal energy swirling around hands, standing in ancient library
--ar 9:16, dnd art, digital art
```

### Локация: Портовая таверна
```
Cozy seaside tavern interior, wooden beams and lanterns, warm firelight, sailors drinking at rough tables, bar counter with bottles, rain visible through windows, evening atmosphere
--ar 16:9, dnd art, digital art
```

### Локация: Мрачный переулок
```
Narrow city alley at night, wet cobblestones reflecting dim lamplight, fog rolling in, shadowy figures in background, ominous atmosphere
--ar 16:9, dnd art, digital art
```

### Предмет: Магический артефакт
```
Ancient grimoire bound in dark leather, glowing purple runes on cover, faint ethereal mist emanating, ornate silver lock and corner reinforcements, resting on wooden pedestal
--ar 1:1, dnd art, digital art, item art
```

### Предмет: Легендарное оружие
```
Ornate longsword with silver blade, glowing blue runes along fuller, golden crossguard shaped like wings, leather-wrapped handle with sapphire pommel, dramatic lighting against dark background
--ar 1:1, dnd art, digital art, item art
```

### Сцена: Засада в переулке
```
Three thugs cornering merchant in dark alley, dynamic action scene, one thug lunging forward, merchant backing against wall, dramatic shadows from single lantern, tense atmosphere
--ar 16:9, dnd art, digital art, dynamic scene
```

---

## Массовая генерация

### Когда пользователь просит серию изображений:

**Пример:** "10 стражников для Сейры"

#### Шаг 1: Определи общие элементы
- Форма: синий табард с эмблемой серебряного якоря
- Организация: Городская стража Сейры
- Стиль: dnd art, digital art
- Соотношение: 9:16 (портреты)

#### Шаг 2: Создай вариации
Варьируй:
- Раса (human, elf, dwarf, half-orc, tiefling...)
- Пол (male, female, non-binary)
- Роль (gate guard, archer, patrol, captain...)
- Эмоция (stern, alert, friendly, weary...)
- Окружение (gate, wall, harbor, market...)

#### Шаг 3: Оформи как таблицу

| # | Раса | Пол | Роль | Промпт |
|---|------|-----|------|--------|
| 1 | Human | M | Gate guard | Human male gate guard, wearing blue tabard with silver anchor emblem, stern expression, standing at city gate, holding spear --ar 9:16, dnd art, digital art |
| 2 | Half-elf | F | Archer | Half-elf female archer, wearing blue guard tabard, alert expression, on stone wall with bow, sea in background --ar 9:16, dnd art, digital art |
| 3 | Dwarf | M | Patrol | Dwarf male guard, blue tabard over chainmail, gruff expression, patrolling harbor docks with lantern --ar 9:16, dnd art, digital art |

**Выдай таблицу пользователю** — удобно для копирования промптов в генератор.

---

## Технические детали

### Соотношения сторон (Aspect Ratio):
- `--ar 9:16` — вертикальный портрет (NPC)
- `--ar 16:9` — горизонтальная панорама (локации, сцены)
- `--ar 1:1` — квадрат (предметы, иконки)
- `--ar 4:3` — классический формат (универсальный)

### Ключевые слова стиля:
- `dnd art` — стиль D&D (обязательно)
- `digital art` — цифровая живопись (обязательно)
- `fantasy art` — фэнтези жанр (опционально)
- `dark fantasy` — мрачная атмосфера (для соответствующих сцен)
- `dynamic scene` — динамичная сцена (для боя/действия)
- `item art` — предметная визуализация (для артефактов)

### Качество (опционально):
- `highly detailed` — высокая детализация
- `atmospheric lighting` — атмосферное освещение
- `cinematic` — кинематографичность

**Не перегружай:** 2-3 ключевых слова достаточно. Базовый набор: `dnd art, digital art`.

---

## Сохранение промптов

### В файле NPC/локации:
Добавь секцию в конец файла:
```markdown
## Промпт для изображения
```
[промпт]
--ar 9:16, dnd art, digital art
```
```

### Отдельный файл для серии:
**Путь:** `!Черновик/prompts_[тема]_[дата].md`

**Формат:**
```markdown
---
type: prompts
topic: Стража Сейры
created: 2026-02-07
author: claude
---

# Промпты: Стража Сейры

## Общие элементы
- Форма: синий табард с эмблемой серебряного якоря
- Стиль: dnd art, digital art
- Соотношение: 9:16

## Промпты

### 1. Привратник
```
Human male gate guard, wearing blue tabard with silver anchor emblem...
--ar 9:16, dnd art, digital art
```

### 2. Лучница
```
Half-elf female archer, wearing blue guard tabard...
--ar 9:16, dnd art, digital art
```

[...]
```

---

## Changelog

При создании промптов добавь changelog в файл NPC/локации:
```markdown
> [!changelog]
> **2026-02-07 (claude):** Добавлен промпт для изображения.
```

---

## Чеклист

- [ ] Определён тип изображения (NPC/локация/предмет/сцена)
- [ ] Собрана информация из контекста
- [ ] Проверены эмблемы и символика
- [ ] Промпт содержит все обязательные элементы
- [ ] Длина промпта оптимальна (30-60 слов)
- [ ] Добавлено правильное соотношение сторон
- [ ] Указан стиль (dnd art, digital art)
- [ ] Промпт добавлен в файл или таблицу

---

**Последнее обновление:** 2026-02-07
**Автор skill:** claude
