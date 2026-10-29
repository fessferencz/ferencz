# Web Design Skills для Codex

Набор Markdown-инструкций для разработки и улучшения веб-интерфейсов. Все файлы открываются прямо в GitHub, VS Code и Codex. Это **документация для ИИ**, а не исполняемый код.

> Внимание: этот репозиторий публичный. Не добавляйте сюда пароли, токены, IP-адреса внутренних серверов, конфигурации доступа, персональные данные и приватные исходники.

## Состав

| Файл | Назначение |
|---|---|
| [AGENTS.md](AGENTS.md) | Постоянные правила Codex в проекте |
| [docs/design-system.md](docs/design-system.md) | Базовая система визуальных и UX-правил |
| [.agents/skills/landing-page-design/SKILL.md](.agents/skills/landing-page-design/SKILL.md) | Проектирование и разработка лендингов |
| [.agents/skills/redesign-existing-projects/SKILL.md](.agents/skills/redesign-existing-projects/SKILL.md) | Дизайн-аудит и точечный редизайн существующих сайтов |
| [.agents/skills/dashboard-ux/SKILL.md](.agents/skills/dashboard-ux/SKILL.md) | Интерфейсы аналитических панелей и внутренних сервисов |
| [.agents/skills/frontend-quality-audit/SKILL.md](.agents/skills/frontend-quality-audit/SKILL.md) | Проверка доступности, адаптивности, состояний и качества |
| [.agents/skills/safe-web-changes/SKILL.md](.agents/skills/safe-web-changes/SKILL.md) | Безопасные изменения на собственных серверах |

## Как подключить к конкретному проекту Codex

1. Откройте в Codex папку **самого веб-проекта**, с которым хотите работать.
2. В корне проекта создайте папку \`.agents/skills/\` и скопируйте туда папки навыков из этого репозитория.
3. Перенесите \`docs/design-system.md\` и **согласуйте/объедините** \`AGENTS.md\` с существующим файлом проекта. Не перезаписывайте действующие инструкции вслепую.
4. Добавьте изменения в Git, проверьте diff и сделайте commit в рабочем репозитории.
5. В Codex проверьте \`/skills\` или вызовите навык, например \`$dashboard-ux\`. Если обновления не видны — перезапустите Codex.

Пример для Linux / macOS (выполнять **в локальной копии проекта, а не на боевом сервере**):

\`\`\`bash
git clone https://github.com/fessferencz/ferencz.git /tmp/ferencz-design-skills
cd /path/to/your/web-project
mkdir -p .agents/skills docs
cp -R /tmp/ferencz-design-skills/.agents/skills/. .agents/skills/
cp -n /tmp/ferencz-design-skills/docs/design-system.md docs/design-system.md
# AGENTS.md нужно просмотреть и при необходимости объединить вручную.
git status
\`\`\`

**Для всех проектов одного пользователя Codex** можно скопировать папки навыков в \`~/.agents/skills/\` на том компьютере, где запущен Codex. Это не тот же самый каталог, что веб-корень на сервере.

**Важно:** добавление файлов в данный репозиторий не делает их автоматически активными во всех остальных репозиториях или на серверах. Их нужно установить в соответствующую рабочую среду.

## Примеры запросов

- \`$landing-page-design Спроектируй страницу онлайн-записи. Сначала предложи структуру и тексты.\`
- \`$redesign-existing-projects Проведи UX-аудит текущего сайта. Пока не меняй код.\`
- \`$dashboard-ux Сделай таблицу показателей удобной для мобильного устройства, сохрани расчёты и API.\`
- \`$frontend-quality-audit Проверь экран: клавиатура, контрастность, мобильный UX, loading/empty/error.\`
- \`$safe-web-changes Подготовь план безопасного обновления и отката, без деплоя.\`

## Принципы

- Сначала диагностика и цель, затем дизайн, реализация и тестирование.
- Действующие бизнес-правила, API, расчёты и доступы сохраняются.
- Не выдумываем клиентов, отзывы, цены и показатели.
- Правила и токены существующего бренда приоритетнее эстетических предпочтений сторонних навыков.
- Никаких изменений на production без явного задания и проверки безопасности.

## Источники и адаптация

Идея и часть подходов адаптированы по:
- [elayadesign/ai-design-skills](https://github.com/elayadesign/ai-design-skills), навык landing-page-design.
- [elayadesign/redesign-skill](https://github.com/elayadesign/redesign-skill), навык redesign-existing-projects.

Содержимое этой подборки — новая адаптированная редакция правил, **не дословная копия** сторонних SKILL.md. Внешние репозитории распространяются под лицензией MIT; перед переносом их полного оригинального кода и файлов сохраняйте соответствующие лицензии и уведомления.

[Официальная документация по навыкам Codex](https://learn.chatgpt.com/docs/build-skills)
