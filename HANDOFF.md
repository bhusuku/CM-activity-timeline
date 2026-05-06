# CM-activity-timeline · HANDOFF после спринта 6 мая 2026

## Что это и зачем

Live-документ еженедельного плана Code Maestro - релизы, маркетинг, работа с клиентами, CM 2.0 / Enterprise. Используется Антоном для синхронизации команды и для отчёта фаундерам (Алексу, Максу). Деплоится автоматически на https://cm-activity-timeline.vercel.app/ через Vercel + GitHub.

Канонический процесс - см. [CLAUDE.md](./CLAUDE.md). Кратко: **один git-репо = одно место правды**, никаких копий в Claude Projects.

## Текущий файл

[`2026-05-06-release-marketing-map.html`](./2026-05-06-release-marketing-map.html) - версия от 6 мая 2026 (среда, weekly sync с разработчиками, обработана через скилл meeting-processor).

Шкала Gantt: **29 Apr - 2 Jun** (5 недель). Линия "Сегодня · 06 May" на `left: 23.33%` (граница Week 1 / Week 2).

## Что было сделано в этом спринте

Файл переделан с версии 22 апреля → 6 мая. Главные структурные изменения:

### 1. Core block переименован
Было: "Большой релиз: связка трёх компонентов" (Unreal + V2 + Asset Studio).
Стало: "Activation Improvements · Web CM · Аналитика" - три параллельных фронта на текущую неделю. Релиз 29 апреля сдвинулся, фокус на стабилизации и Web CM.

### 2. CM 2.0 / Enterprise track → перенесён вниз
По решению Антона - сделать акцент на Web CM (новый фокус), CM 2.0 ушёл в номинальный компактный блок после Owners panel. Содержимое: разработка ongoing (Вова), дата TBD, обзорное видео CM-1570, advisor Сергей, Webinar Playable Ads (идея).

### 3. Web CM стал самостоятельным треком
Раньше был внутри Enterprise. Теперь отдельный track в Map view + отдельная Gantt-категория. Содержит: research-спринт Саши Басюка (LLM cost test, HTML protection, analytics traces), CM-1596 Simple/Advanced playable paths (Вова), анти-абьюз research, получение фидбэка по прототипу.

### 4. Gantt categories переупорядочены
Финальный порядок: Activation Improvements → Churn Reduction → Клиенты-фидбэк-рассылки → Web CM → Аналитика и инфра → Контент и маркетинг → CM 2.0/Enterprise.

### 5. Алекс убран из Owners panel
По запросу Антона.

### 6. Новые секции
- **Маркетинг (план Бори)** в Playable Ads track: LinkedIn Ads, Google Ads, Vendo рассылка, анонсы TG/LinkedIn/Reddit, лендинг с Demo, новый формат отчёта для Demo, ньюслеттер.
- **Churn Reduction** (отдельная Gantt-категория, всё на 30 Apr - 09 May или 06-12 May): CM-1540, CM-1541, CM-1542, CM-1579, CM-1563 - все на Колю, реальные названия из Jira.
- **Playable Analytics** упрощён: вместо отдельных питчей Triple Dot и Azur Games - один пункт "15 фоллоуапов по участникам feedback программы" (Антон, 09-12 May).
- **CM 2.0 / Enterprise** компактный блок после Owners.

### 7. CM-1572 и CM-1582 перенесены в Activation Improvements
Раньше были в Аналитике, Антон попросил перенести (т.к. напрямую связаны с активацией). В Аналитике остались PostHog setup и Intercom integration.

### 8. Newsletter перевели на Антона
Раньше был в Бориных задачах, Антон взял на себя (11-12 May).

### 9. Финальные даты задач (ключевые)
- CM-1573 review installer · Леонид · 05-12 May
- CM-1585 Подпись Windows · Леонид · 06-09 May
- CM-1593 Создать installer/uninstaller Windows · Вова · 05-12 May
- CM-1595 Mac installer/uninstaller · Леонид · 13-19 May
- CM-1572 Аудит Amplitude · Вал · 07-09 May
- CM-1582 Глоссарий событий · Вал · 07-09 May
- CM-1540/1541/1542 Churn Day 1/5/14 · Коля · 30 Apr - 09 May
- CM-1579 Заменить хардкод RETURN40 · Коля · 06-12 May
- CM-1563 Tally → backend · Коля · 11-12 May (опционально)
- CM-1567 Короткие demo Unreal · Вова · 06-12 May (первые 3 до 07.05)
- CM-1596 Simple/Advanced paths · Вова · 09-19 May
- CM-1570 Обзорное видео CM 2.0 · Вова · 20-26 May
- LinkedIn Ads / Google Ads · Боря · 04-12 May
- Анонсы TG/LinkedIn/Reddit · Боря · 05-12 May
- Лендинг с Demo · Боря · 05-19 May
- Vendo рассылка · Боря · 06-12 May
- Newsletter обновления · Антон · 11-12 May
- Новый формат отчёта для Demo · Боря+Антон · 29 Apr - 12 May
- Tutorial Playable · Антон · 09-12 May
- Реактивационная рассылка · Коля+Антон · 11-12 May
- Ручная рассылка trial-юзерам (330) · Коля+Антон · 09-12 May
- Special offer для Power Users (11) · Антон · 09-12 May
- Playable Analytics 15 фоллоуапов · Антон · 09-12 May
- Получение фидбэка по прототипу Web CM · Антон · 13-19 May
- Контрольный замер App Boot → Login · 12 May (milestone)

### 10. CM-1581 (Reactivation имплементация) - **не в timeline**
Видимо забыли явно положить. Если нужно - добавить либо в Churn Reduction, либо в Activation Improvements (Коля).

## Открытые вопросы / TODO

1. **Деплой текущей версии** - сейчас файл уже в main, но возможно нужен новый commit. Проверить `git status` / `git log`.
2. **CM-1581** (Reactivation имплементация Коли) - добавить в timeline?
3. **CM-1580 vs CM-1582**: я взял CM-1582 (предполагаемая опечатка ASR при переносе в Activation). CM-1580 уже Done. Подтвердить.

## Связанные артефакты вне репо

- Полный контекст встречи 6 мая (digest + jira-task drafts + chat-update drafts) - `~/Documents/Claude/Projects/Сlaude_Code_Maestro/Automation Actions/2026-05-06-cm-weekly-sprint-tasks/`
- Скилл meeting-processor (как обрабатывать будущие транскрипты) - `~/Documents/Claude/Projects/Сlaude_Code_Maestro/.claude/skills/meeting-processor/SKILL.md`
- Глобальный CLAUDE.md проекта Code Maestro - `~/Documents/Claude/Projects/Сlaude_Code_Maestro/CLAUDE.md`

## Как продолжать в новом чате

1. Открой Cowork с подключённой папкой `~/Documents/GitHub/CM-activity-timeline/`.
2. Claude автоматически прочитает [CLAUDE.md](./CLAUDE.md) - это вся инструкция работы с файлом.
3. Если нужен полный контекст спринта - попроси Claude прочитать [HANDOFF.md](./HANDOFF.md) (этот файл).
4. Перед любыми правками - `git pull` (на всякий случай).
5. После правок - `git add . && git commit -m "..." && git push origin main` → Vercel auto-deploy.

## Шпаргалка по позиционированию в Gantt

См. [CLAUDE.md § "Таблица процент → день"](./CLAUDE.md). Кратко:
- Шкала 5 недель = 100%
- 1 день = 3.33%
- Day 0 (29 Apr в текущей шкале) = `left: 0%`
- Сегодня (06 May) = `left: 23.33%`

Пример: задача 09-12 May → `left: 33.33%; width: 13.34%`.
