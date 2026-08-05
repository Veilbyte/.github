# Veilbyte GitHub Organization Policy Pack

Версия / Version: **1.1**  
Дата / Date: **2026-08-05**

> **Deployment status:** the base policy pack is installed for Veilbyte. Dedicated security, general, and brand email/Telegram contacts are not configured yet; until then, use GitHub Private Vulnerability Reporting for vulnerabilities and contact `@Onmaynec` privately for other sensitive matters.

Готовый комплект политик и шаблонов для публичного репозитория организации `Veilbyte/.github`.

This is a ready-to-adapt policy and template pack for the public `Veilbyte/.github` organization repository.

## Миссия / Mission

**RU:** Veilbyte создаёт независимые, безопасные и удобные технологии, которые возвращают пользователям контроль над цифровой средой.

**EN:** Veilbyte builds independent, secure, and usable technologies that return control of the digital environment to users.

**Слоган / Tagline:** **Own your digital layer.**

## Как развернуть / Deployment

1. Создайте в организации публичный репозиторий с точным именем `.github`.
2. Скопируйте содержимое этого пакета в корень репозитория.
3. Заполните контакты в `CONTACTS_TO_FILL.md` и замените маркеры во всех документах.
4. Создайте команды, указанные в `docs/GITHUB_SETTINGS_CHECKLIST_RU.md`.
5. Скопируйте `CODEOWNERS.template` в `.github/CODEOWNERS` внутри репозитория `.github`, затем отдельно добавляйте адаптированный `CODEOWNERS` в каждый проектный репозиторий, где нужны code-owner reviews.
6. Убедитесь, что Issue Forms находятся в `.github/ISSUE_TEMPLATE/`.
7. Настройте rulesets, Actions и security-функции по чек-листу.
8. Для каждого репозитория выберите отдельную лицензию. По умолчанию используйте ограниченную source-available модель только после юридической проверки.

1. Create a public organization repository named exactly `.github`.
2. Copy this package into the repository root.
3. Complete `CONTACTS_TO_FILL.md` and replace the placeholders in all documents.
4. Create the teams listed in the settings checklist.
5. Copy `CODEOWNERS.template` to `.github/CODEOWNERS` in the `.github` repository, then add a repository-specific `CODEOWNERS` file to every project that requires code-owner reviews.
6. Ensure Issue Forms are stored under `.github/ISSUE_TEMPLATE/`.
7. Configure rulesets, Actions, and security features using the checklist.
8. Choose a repository-specific license for every repository. Use the restricted source-available template only after legal review.

## Состав / Contents

- `ORGANIZATION_POLICY.md` — общая политика организации.
- `GOVERNANCE.md` — роли, полномочия и принятие решений.
- `CONTRIBUTING.md` — порядок внесения изменений.
- `CODE_OF_CONDUCT.md` — правила поведения и модерации.
- `SECURITY.md` — безопасное раскрытие уязвимостей.
- `SUPPORT.md` — поддержка пользователей и версий.
- `RESPONSIBLE_USE.md` — допустимое использование сетевых и security-проектов.
- `BRAND_POLICY.md` — правила использования названия и логотипа.
- `CONTRIBUTOR_LICENSE_AGREEMENT.md` — упрощённое соглашение с участниками.
- `LICENSE_TEMPLATE_RESTRICTED.md` — шаблон ограниченной лицензии.
- `.github/ISSUE_TEMPLATE/` и `PULL_REQUEST_TEMPLATE.md` — шаблоны GitHub.
- `templates/` — шаблоны README, CHANGELOG и политики репозитория.
- `docs/` — чек-листы настроек и матрица ролей.

## Важное юридическое замечание / Legal notice

Этот пакет является рабочим организационным шаблоном, а не юридической консультацией. Ограниченная лицензия и CLA должны быть проверены юристом с учётом страны владельца, места регистрации будущей компании, правил экспорта технологий, санкционного законодательства и особенностей конкретных продуктов.

This pack is an operational template, not legal advice. The restricted license and CLA should be reviewed by qualified counsel for the owner's jurisdiction, any future company jurisdiction, technology export rules, sanctions requirements, and the characteristics of each product.
