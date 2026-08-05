# Политика GitHub-организации Veilbyte

Версия: **1.0**  
Дата вступления в силу: **5 августа 2026 года**

## 1. Назначение

Veilbyte — принадлежащая владельцу GitHub-организация для разработки приложений, сетевых инструментов, средств информационной безопасности, технологий работы в условиях сетевых ограничений, мессенджеров, библиотек и будущих смежных продуктов.

Миссия Veilbyte: **создавать независимые, безопасные и удобные технологии, которые возвращают пользователям контроль над цифровой средой**.

Ценности Veilbyte: свобода, приватность, безопасность, открытость процессов, качество, независимость, прозрачность, удобство и технологичность.

Слоган: **Own your digital layer.**

## 2. Модель организации

1. Организация принадлежит владельцу, указанному как единственный GitHub Organization Owner.
2. В организации могут находиться публичные и приватные репозитории.
3. Участниками могут быть постоянные члены команды и приглашённые разработчики.
4. Окончательные решения по доступам, спорным вопросам, передаче репозиториев, лицензированию и бренду принимает владелец.
5. Эта политика является общей для всех репозиториев. Репозиторий может вводить более строгие правила, но не более слабые без явного решения владельца.

## 3. Классификация репозиториев

Каждый репозиторий должен иметь один из статусов:

- **Private** — закрытая внутренняя разработка;
- **Public Source-Available** — исходный код доступен для просмотра, но права использования ограничены лицензией;
- **Open Source** — проект опубликован под явно указанной OSI-совместимой лицензией;
- **Experimental** — прототип или исследовательский проект без гарантий стабильности;
- **Archived** — проект не развивается и доступен только в режиме чтения.

Публичный доступ к исходному коду сам по себе не делает проект open source. Если репозиторий не содержит явной открытой лицензии, он не должен называться open source.

## 4. Интеллектуальная собственность и лицензирование

1. Для каждого репозитория обязателен отдельный файл `LICENSE`.
2. По умолчанию код Veilbyte нельзя использовать, копировать, изменять, распространять, включать в другие продукты или применять коммерчески без отдельного письменного разрешения владельца.
3. Коммерческое использование может быть разрешено отдельным соглашением.
4. Любое разрешённое использование должно сохранять указание Veilbyte, сведения об авторских правах и ссылку на оригинальный репозиторий, если соглашением не установлено иное.
5. Владелец может отдельно выбрать открытую лицензию для конкретной библиотеки или проекта. В этом случае условия конкретного `LICENSE` имеют приоритет.
6. Название, логотип, визуальный стиль и иные обозначения Veilbyte не лицензируются вместе с кодом.
7. Публикация кода на GitHub не означает отказа от прав.

## 5. Обязательные файлы

Каждый публичный репозиторий должен содержать:

- `README.md`;
- `LICENSE`;
- `CONTRIBUTING.md`;
- `SECURITY.md`;
- `CODE_OF_CONDUCT.md`;
- `CHANGELOG.md`.

Допускается наследование общих community health files из публичного репозитория `Veilbyte/.github`, однако `README.md`, `LICENSE` и специфичная для проекта информация должны находиться в самом репозитории.

## 6. Создание и управление репозиториями

1. Новые репозитории создают владелец или явно назначенные администраторы.
2. Удалять, передавать, архивировать или менять видимость репозитория может только владелец.
3. Единого формата названий нет, но название должно быть понятным, уникальным и не вводить пользователей в заблуждение.
4. Секреты, токены, ключи, персональные данные и закрытые конфигурации запрещено хранить в Git.
5. Публичность репозитория не должна включаться до проверки истории Git и удаления чувствительных данных.

## 7. Ветки и изменения

Основная модель веток:

- `main` — стабильное состояние;
- `develop` — интеграционная ветка;
- `feature/*` — новые функции;
- `fix/*` — исправления;
- `release/*` — подготовка релизов;
- `hotfix/*` — срочные исправления стабильной версии.

Любые изменения в `main` и `develop` выполняются через Pull Request. Прямые push, force push и удаление защищённых веток запрещены. Владелец может использовать bypass в исключительных случаях, но причина должна быть описана в Pull Request, Issue или журнале релиза.

## 8. Проверка Pull Request

1. Число одобрений определяется проектом:
   - обычные изменения — по умолчанию 1 одобрение;
   - изменения безопасности, криптографии, сетевого ядра, механизма обновлений, сборки и релизов — по умолчанию 2 одобрения;
   - репозиторий с одним активным разработчиком — допускается 0 независимых одобрений, но PR и обязательные проверки сохраняются.
2. Перед слиянием должны успешно пройти применимые проверки: сборка, тесты, линтер, форматирование, анализ зависимостей, поиск секретов и security-анализ.
3. Автор PR может выполнить слияние после выполнения всех правил и одобрений.
4. По умолчанию используется `squash merge` для `feature/*` и `fix/*`.
5. `merge commit` используется для `release/*`, `hotfix/*` и случаев, когда необходимо сохранить структуру истории.
6. Rebase merge не является стандартным способом слияния.
7. Коммиты в защищённые ветки должны быть подписаны и иметь статус Verified.

## 9. Коммиты и качество кода

1. Используется Conventional Commits. Тип пишется на английском, описание — на русском:
   - `feat: добавлена проверка URL`;
   - `fix: исправлен сбой при запуске`;
   - `docs: обновлена документация`;
   - `refactor: переработан модуль анализа`.
2. Код должен соответствовать правилам форматирования, линтинга и архитектуры репозитория.
3. AI-сгенерированный код разрешён только при условии, что автор:
   - понимает его работу;
   - проверил происхождение и лицензионные риски;
   - протестировал изменение;
   - несёт за него ту же ответственность, что и за написанный вручную код.
4. Непроверенный или непонятный автору AI-код не принимается.

## 10. Issues и Discussions

Issues используются для ошибок, запросов функций, задач разработки, вопросов и проблем документации. Discussions используются для общих обсуждений, идей и поддержки, не требующей конкретного изменения кода.

Обращения могут быть закрыты без дальнейшего рассмотрения, если они:

- не заполнены по шаблону;
- дублируют существующее обращение;
- не содержат воспроизводимых данных;
- не относятся к проекту;
- нарушают правила поведения;
- публично раскрывают уязвимость или чувствительные данные.

Запросы функций, связанных с сетевыми ограничениями, разрешены при соблюдении законодательства и `RESPONSIBLE_USE.md`.

## 11. Безопасность

1. Уязвимости нельзя публиковать в Issues, Discussions или публичных чатах.
2. Предпочтительный канал — GitHub Private Vulnerability Reporting.
3. Дополнительные приватные каналы будут опубликованы после их официального создания.
4. Veilbyte стремится подтвердить получение корректного сообщения в течение 72 часов.
5. Исследователь может публично раскрыть информацию после согласованного исправления или после отдельного письменного согласования.
6. Безопасное исследование не должно включать повреждение данных, доступ к чужим аккаунтам, социальную инженерию, отказ в обслуживании, закрепление в системах или публикацию данных пользователей.

## 12. Доступ и роли

Используются роли Owner, Administrator, Maintainer, Developer, Reviewer и External Contributor. Доступ выдаётся по принципу минимально необходимых прав.

- Приглашать и удалять участников может только владелец.
- Административные права требуют отдельного решения владельца.
- Автоматическое снятие доступа не используется; владелец проводит ручную периодическую проверку.
- Обязательная 2FA на уровне организации пока не применяется, но настоятельно рекомендуется каждому участнику.
- Единственным Organization Owner остаётся владелец, принимающий связанный с этим риск восстановления доступа.

## 13. Релизы и версии

1. Используется Semantic Versioning: `MAJOR.MINOR.PATCH`.
2. Релиз может публиковать участник с ролью Developer или выше, если он работает над проектом и имеет явное право публикации релизов.
3. Автоматические релизы через GitHub Actions разрешены.
4. Официальные бинарные сборки должны создаваться официальным CI либо иметь проверяемую связь с исходным кодом и тегом.
5. Release notes, контрольные суммы, подписи артефактов и статусы Alpha/Beta/Stable не являются обязательными на уровне организации, но могут быть обязательными в конкретном проекте.
6. По умолчанию поддерживается текущая стабильная major-версия и предыдущая major-версия в течение 6 месяцев после выхода новой. Критические security-исправления для старых версий выпускаются по возможности и решению команды.
7. О прекращении поддержки необходимо объявить заранее в README, CHANGELOG, Discussion или релизе.

## 14. Зависимости и supply chain

1. Dependency Graph, Dependabot alerts и автоматические security PR должны быть включены, когда доступны.
2. Неактивная зависимость допускается только при документированном обосновании, отсутствии приемлемой замены и наличии мер снижения риска.
3. Зависимость с известной неисправленной уязвимостью уровня High или Critical не допускается без решения владельца и документированной компенсационной меры.
4. Совместимость лицензий проверяется на уровне проекта; отсутствие автоматического запрета не отменяет обязанность проверки.
5. Lock-файлы не обязательны на уровне всей организации, но проект может сделать их обязательными.
6. Секреты CI должны храниться в GitHub Secrets или защищённых environments с минимальной областью доступа.

## 15. Неактивные и архивные проекты

1. Репозиторий рассматривается на предмет статуса maintenance mode после 12 месяцев без значимых коммитов, релизов или подтверждённого плана работ.
2. Перед архивацией публикуется уведомление минимум за 30 дней, фиксируется последняя рекомендуемая версия и известные ограничения.
3. Архивировать или передавать репозиторий может только владелец.
4. Продолжение проекта через fork допускается, если это разрешено его лицензией либо владелец дал отдельное письменное разрешение, в том числе в уведомлении об архивации.
5. Форк не может использовать название и логотип Veilbyte и не должен выдаваться за официальный.

## 16. Изменение политики

Владелец может изменить настоящую политику. Существенные изменения публикуются в истории репозитория `.github`. Правила конкретного репозитория могут уточнять эту политику, но не отменяют требования безопасности, прав на код и бренд.

---

# Veilbyte GitHub Organization Policy

Version: **1.0**  
Effective date: **August 5, 2026**

## 1. Purpose

Veilbyte is an owner-controlled GitHub organization for applications, networking tools, information security projects, technologies for restricted network environments, messaging platforms, libraries, and future adjacent products.

Veilbyte's mission is to **build independent, secure, and usable technologies that return control of the digital environment to users**.

Core values: freedom, privacy, security, process openness, quality, independence, transparency, usability, and technological excellence.

Tagline: **Own your digital layer.**

## 2. Organization model

1. The organization is controlled by the owner, who remains the sole GitHub Organization Owner.
2. The organization may contain both public and private repositories.
3. Participation is available to permanent team members and invited developers.
4. The owner makes final decisions on access, disputes, repository transfers, licensing, and brand use.
5. This policy applies to every repository. A repository may adopt stricter rules, but may not weaken this policy without explicit owner approval.

## 3. Repository classification

Every repository must be classified as one of the following:

- **Private** — internal development;
- **Public Source-Available** — source is visible, but use is restricted by license;
- **Open Source** — explicitly licensed under an OSI-compatible license;
- **Experimental** — prototype or research project without stability guarantees;
- **Archived** — read-only and no longer actively developed.

Public source visibility does not by itself make a project open source. A repository without an explicit open-source license must not be described as open source.

## 4. Intellectual property and licensing

1. Every repository must contain its own `LICENSE` file.
2. By default, Veilbyte code may not be used, copied, modified, distributed, included in another product, or used commercially without separate written permission from the owner.
3. Commercial use may be authorized under a separate agreement.
4. Any authorized use must preserve Veilbyte attribution, copyright notices, and a link to the original repository unless an agreement states otherwise.
5. The owner may select an open-source license for a specific library or project. The repository-specific `LICENSE` then takes precedence.
6. Veilbyte's name, logo, visual identity, and other marks are not licensed with the code.
7. Publishing source code on GitHub does not waive any rights.

## 5. Required files

Every public repository must contain:

- `README.md`;
- `LICENSE`;
- `CONTRIBUTING.md`;
- `SECURITY.md`;
- `CODE_OF_CONDUCT.md`;
- `CHANGELOG.md`.

Common community health files may be inherited from the public `Veilbyte/.github` repository, but project-specific `README.md`, `LICENSE`, and product information must remain in each repository.

## 6. Repository creation and administration

1. Repositories may be created by the owner or explicitly appointed administrators.
2. Only the owner may delete, transfer, archive, or change repository visibility.
3. No mandatory repository naming convention is imposed, but names must be clear, unique, and non-misleading.
4. Secrets, tokens, keys, personal data, and private configuration must never be committed.
5. A repository must not be made public until its Git history has been reviewed for sensitive content.

## 7. Branches and changes

Standard branches:

- `main` — stable state;
- `develop` — integration branch;
- `feature/*` — features;
- `fix/*` — fixes;
- `release/*` — release preparation;
- `hotfix/*` — urgent stable fixes.

All changes to `main` and `develop` must go through Pull Requests. Direct pushes, force pushes, and deletion of protected branches are prohibited. The owner may bypass rules in exceptional cases, but the reason must be documented in a Pull Request, Issue, or release record.

## 8. Pull Request review

1. Required approvals depend on the project:
   - standard changes: 1 approval by default;
   - security, cryptography, networking core, updater, build, or release changes: 2 approvals by default;
   - a single-maintainer repository may use 0 independent approvals, while retaining the PR and required-check workflow.
2. Applicable build, test, lint, formatting, dependency, secret, and security checks must pass before merge.
3. The PR author may merge after all requirements are satisfied.
4. `squash merge` is the default for `feature/*` and `fix/*`.
5. `merge commit` is used for `release/*`, `hotfix/*`, and cases where branch history must be preserved.
6. Rebase merge is not a standard merge method.
7. Commits reaching protected branches must be signed and show as Verified.

## 9. Commits and code quality

1. Conventional Commits are required. The type is in English and the description is in Russian.
2. Code must follow repository formatting, linting, architecture, and testing rules.
3. AI-generated code is allowed only when the author understands it, checks provenance and licensing risk, tests it, and accepts full responsibility.
4. Unreviewed or unexplained AI-generated code is not accepted.

## 10. Issues and Discussions

Issues are used for bugs, feature requests, development tasks, questions, and documentation problems. Discussions are used for broader ideas and support that does not yet require a code change.

Reports may be closed without further action when they are incomplete, duplicated, unreproducible, unrelated, abusive, or disclose vulnerabilities or sensitive data publicly.

Feature requests related to network restrictions are permitted only when consistent with applicable law and `RESPONSIBLE_USE.md`.

## 11. Security

1. Vulnerabilities must not be posted in Issues, Discussions, or public chats.
2. GitHub Private Vulnerability Reporting is the preferred channel.
3. Additional private channels will be published after they are officially created.
4. Veilbyte aims to acknowledge a valid report within 72 hours.
5. A researcher may disclose a vulnerability publicly after a coordinated fix or separate written agreement.
6. Safe research excludes data damage, access to other users' accounts, social engineering, denial of service, persistence, and disclosure of user data.

## 12. Access and roles

Veilbyte uses Owner, Administrator, Maintainer, Developer, Reviewer, and External Contributor roles. Access follows least privilege.

- Only the owner may invite or remove participants.
- Administrative access requires a separate owner decision.
- Access is not revoked automatically; the owner performs periodic manual reviews.
- Organization-wide 2FA is not currently mandatory, but is strongly recommended.
- The owner remains the sole Organization Owner and accepts the associated account-recovery risk.

## 13. Releases and versions

1. Semantic Versioning is used: `MAJOR.MINOR.PATCH`.
2. A project participant with Developer access or higher may publish releases when explicitly authorized for that repository.
3. Automated releases through GitHub Actions are permitted.
4. Official binaries must be produced through official CI or have a verifiable link to source and a release tag.
5. Release notes, checksums, artifact signatures, and Alpha/Beta/Stable labels are not mandatory organization-wide, but may be required by a repository.
6. By default, Veilbyte supports the current stable major version and the previous major version for six months after the next major release. Backports of critical security fixes are best-effort.
7. End-of-support notices must be published in advance.

## 14. Dependencies and supply chain

1. Dependency Graph, Dependabot alerts, and automated security updates should be enabled where available.
2. An unmaintained dependency may be used only with documented justification, no acceptable replacement, and risk mitigations.
3. A dependency with an unresolved High or Critical vulnerability requires owner approval and documented compensating controls.
4. License compatibility remains a project responsibility.
5. Lock files are not mandatory organization-wide, but a project may require them.
6. CI secrets must be stored in GitHub Secrets or protected environments with minimal scope.

## 15. Inactive and archived projects

1. A repository is reviewed for maintenance mode after 12 months without meaningful commits, releases, or a confirmed roadmap.
2. At least 30 days before archival, the project must publish a notice, identify the last recommended version, and list known limitations.
3. Only the owner may archive or transfer a repository.
4. A fork may continue the project where the license permits or where the owner grants separate written permission, including in the archival notice.
5. A fork may not use Veilbyte branding or imply official status.

## 16. Policy changes

The owner may amend this policy. Material changes are recorded in the `.github` repository history. Repository-specific policies may clarify these rules but may not waive security, intellectual-property, or brand protections.
