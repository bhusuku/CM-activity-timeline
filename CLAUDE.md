# CM-activity-timeline · контекст для Claude

Этот репозиторий - **единственный источник правды** для еженедельного релиз/маркетинг-плана Code Maestro. Деплой идёт через Vercel (https://cm-activity-timeline.vercel.app/), привязка к GitHub - автоматический deploy на push в main.

## Что лежит в репо

- `<YYYY-MM-DD>-release-marketing-map.html` - актуальный план недели. Версионируется по дате weekly sync. Текущая - [2026-05-06-release-marketing-map.html](./2026-05-06-release-marketing-map.html).
- `vercel.json` - rewrite root URL на актуальный HTML.
- `HANDOFF.md` - подробный summary последнего спринта, открытые вопросы, формат правок.

## Канонический процесс работы

1. **Один каталог = один проект.** Работаем только из этого git-репо. Никаких копий в `~/Documents/Claude/Projects/`.
2. **Перед правками:** `git pull` (чтобы не затереть deploy с другой машины).
3. **Правки:** редактирование HTML напрямую (Edit tool, python-script, sed - что удобнее по объёму).
4. **Новая версия плана** - копировать актуальный HTML в `<новая-дата>-release-marketing-map.html`, обновить `vercel.json` (rewrite destination).
5. **Деплой:** `git add . && git commit -m "..." && git push origin main` → Vercel auto-deploy на main.
6. **Черновики/эксперименты:** через ветку (`update-map`), смотрим preview-URL от Vercel (комментится в PR), потом merge.

## Структура HTML-файла

Два таба (Gantt active по умолчанию, Детали = Map view):

**Map view:**
- Header (Weekly Sync · DD.MM.YYYY)
- Core block (3 главных фокуса недели)
- Two tracks: Playable Ads + Web CM (или Enterprise - в зависимости от фокуса)
- Customers panel + Timeline panel (5 пунктов "что когда")
- Owners panel (роль + текущий focus, без Алекса - Антон убрал 6 мая)
- Compact CM 2.0 / Enterprise блок внизу (номинальная фоновая работа)

**Gantt:**
- 5 weeks по 7 дней (последняя - дробная). Шкала: текущая неделя начинается с **left: 23.33%**.
- Категории в порядке: Activation Improvements → Churn Reduction → Клиенты-фидбэк-рассылки → Web CM → Аналитика и инфра → Контент и маркетинг → CM 2.0/Enterprise.
- Красная вертикаль = "Сегодня" (на дату weekly sync).
- Bar style: `gantt-bar release` (gold), `content` (orange), `customer` (blue), `enterprise` (violet), `idea` (dashed violet).

### Таблица процент → день для Gantt

Шкала 5 недель = 100%. 1 неделя = 23.33%. 1 день = 3.33%. Day 1 шкалы = `left: 0%`.

Например, если шкала 29 Apr - 2 Jun:
- 29 Apr = 0% · 5 May = 20% · 6 May = 23.33% · 12 May = 43.33% · 13 May = 46.67%

Width = `(end_day - start_day + 1) × 3.33%` (включительно).

## Стиль и правила

- **Цвета и типографика** - только переменные из `:root` в `<style>` (`--gold`, `--violet`, `--orange`, `--card`, `--text`, и т.д.). Не вводить новые цвета без необходимости.
- **Шрифты** - Montserrat для основного, Inter для заголовков/badge. Подгружаются из Google Fonts.
- **Тире** - всегда короткое `-`, никогда `—` или `–`.
- **Имена команды** - канонические (Расим, не Росим; Леня, не Леонид-вариант; Боря, Коля, Вал, Вова, Саша Басюк, Антон, Алекс, Даня).
- **Полные названия Jira-тикетов** - брать через **Atlassian MCP** (`mcp__...__getJiraIssue`), не выдумывать. Cloud ID: `ilogosgamestudios.atlassian.net`.

## Ссылки на источники контекста

- Полный контекст Code Maestro проекта: `~/Documents/Claude/Projects/Сlaude_Code_Maestro/CLAUDE.md`
- Папка обработанных встреч: `~/Documents/Claude/Projects/Сlaude_Code_Maestro/Automation Actions/`
- Скилл meeting-processor: `~/Documents/Claude/Projects/Сlaude_Code_Maestro/.claude/skills/meeting-processor/SKILL.md`
- Полный playbook meeting-processor: `~/Documents/Claude/Projects/Сlaude_Code_Maestro/Automation Actions/_meeting-processor.md`

## Если что-то не понятно

- Структуру предыдущей версии можно посмотреть в `git log` + `git show`.
- Полный summary последнего спринта (что менялось 6 мая) - в [HANDOFF.md](./HANDOFF.md).
- Если правки приходят голосом/через ASR - могут быть опечатки в номерах тикетов и именах. Сверяйся с Jira (через MCP) и переспрашивай если разница > 1 цифры.
