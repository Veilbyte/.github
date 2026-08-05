# Точный чек-лист настройки GitHub Organization Veilbyte

Дата: **5 августа 2026 года**. Названия пунктов интерфейса GitHub могут немного отличаться в зависимости от плана и обновлений.

## A. Создание публичного `.github`-репозитория

- [ ] Создать публичный репозиторий `Veilbyte/.github`.
- [ ] Загрузить в него файлы этого пакета.
- [ ] Убедиться, что `profile/README.md` отображается на странице организации.
- [ ] Заполнить контакты из `CONTACTS_TO_FILL.md`.
- [ ] Создать команды до активации `CODEOWNERS.template`.
- [ ] Убедиться, что Issue Forms расположены в `.github/ISSUE_TEMPLATE/`.
- [ ] Для репозитория `.github` скопировать `CODEOWNERS.template` в `.github/CODEOWNERS`.
- [ ] В каждый проектный репозиторий отдельно добавить адаптированный `.github/CODEOWNERS`: файл из `Veilbyte/.github` не наследуется другими репозиториями.
- [ ] Команды, указанные в `CODEOWNERS`, должны быть Visible и иметь явный Write-доступ к соответствующему репозиторию; Secret-команды в CODEOWNERS не использовать.

## B. Organization → Settings → General / Profile

- [ ] Display name: `Veilbyte`.
- [ ] Description: `Independent, secure and usable technologies. Own your digital layer.`
- [ ] Добавить итоговую чёрно-белую аватарку.
- [ ] Добавить общий email после его создания.
- [ ] Проверить, что приватные участники не отображаются публично без необходимости.

## C. Member privileges

Рекомендуемые значения:

- [ ] Base permissions: **No permission** для максимального принципа least privilege.
- [ ] Repository creation: отключить для обычных Members.
- [ ] Создание репозиториев выполнять владельцем; администраторам выдавать право через подходящую роль/процесс, если план GitHub это поддерживает.
- [ ] Repository deletion: запретить Members.
- [ ] Repository transfer: запретить Members.
- [ ] Repository visibility change: запретить Members.
- [ ] Issue deletion: запретить обычным Members, если доступен отдельный переключатель.
- [ ] Private repository forking: выключить по умолчанию; включать на уровне проекта при необходимости.
- [ ] Pages creation: ограничить доверенными репозиториями.

## D. Authentication security

Выбранная политика пользователя:

- [ ] Не включать обязательную 2FA на уровне организации на первом этапе.
- [ ] Проверять вручную наличие 2FA у участников и настоятельно рекомендовать passkey/security key/authenticator.
- [ ] Владелец обязан включить 2FA и сохранить recovery codes офлайн.
- [ ] Владелец должен добавить минимум два независимых способа восстановления аккаунта.

Принятый риск: единственный Organization Owner создаёт single point of failure. Решение соответствует выбранной модели, но должно пересматриваться перед запуском коммерчески критичных проектов.

## E. Teams

Создать команды:

- [ ] `administrators` — repository Admin только для назначенных проектов.
- [ ] `maintainers` — repository Maintain.
- [ ] `developers` — repository Write.
- [ ] `reviewers` — repository Triage или Read + право review.
- [ ] `security` — доступ только к security-процессам и нужным приватным репозиториям.

Настройки:

- [ ] Team visibility: `security` и `administrators` можно оставить Secret; `maintainers` и другие команды, используемые в CODEOWNERS, должны быть Visible.
- [ ] Team maintainers назначаются только владельцем.
- [ ] Outside collaborators не добавляются в команды; им выдаётся доступ только к конкретному репозиторию.

## F. Actions → General

- [ ] Разрешить GitHub Actions.
- [ ] Предпочтительно выбрать **Allow Veilbyte actions and reusable workflows, and selected verified actions**.
- [ ] Запрещать Actions из неизвестных источников без review.
- [ ] В workflow фиксировать сторонние Actions на полный commit SHA, где это возможно.
- [ ] Default workflow permissions: **Read repository contents**.
- [ ] `Allow GitHub Actions to create and approve pull requests`: выключено по умолчанию; включать только для проверенного release/dependency workflow.
- [ ] Fork pull request workflows не получают secrets без ручного одобрения.
- [ ] Organization secrets выдавать только выбранным репозиториям, не `All repositories`.
- [ ] Для production/release создать protected Environments с required reviewers.

## G. Personal access tokens, GitHub Apps и OAuth

- [ ] Предпочитать fine-grained PAT вместо classic PAT.
- [ ] Требовать approval fine-grained PAT, если настройка доступна.
- [ ] Ограничить lifetime токенов разумным сроком, например 90 дней, если поддерживается планом.
- [ ] Ежеквартально проверять authorized GitHub Apps и OAuth Apps.
- [ ] Удалять неиспользуемые deploy keys и installation tokens.
- [ ] Не использовать личный PAT владельца в постоянном CI, если доступен GitHub App или `GITHUB_TOKEN`.

## H. Repository defaults

Для каждого репозитория:

- [ ] Default branch: `main`.
- [ ] Создать `develop` после инициализации проекта.
- [ ] Разрешить **Squash merging**.
- [ ] Разрешить **Merge commits**.
- [ ] Отключить **Rebase merging**.
- [ ] Включить **Automatically delete head branches**.
- [ ] Включить Issues.
- [ ] Включить Discussions для публичных пользовательских проектов.
- [ ] Wiki включать только при реальной необходимости.
- [ ] Projects включать на уровне активных проектов.
- [ ] Заполнить About, topics, website и description.
- [ ] Добавить обязательные community files и проектный `LICENSE`.

## I. Ruleset для `main`

Organization Settings → Repository → Rulesets либо Repository Settings → Rules → Rulesets.

Target: default branch / `main`.

- [ ] Enforcement status: Active.
- [ ] Restrict deletions.
- [ ] Block force pushes.
- [ ] Require a pull request before merging.
- [ ] Required approvals: значение проекта; стандарт 1.
- [ ] Для security/network/crypto/updater/build/release проектов: 2 approvals.
- [ ] Dismiss stale pull request approvals when new commits are pushed.
- [ ] Require review from Code Owners для критичных путей.
- [ ] Require approval of the most recent reviewable push, если команда больше одного человека.
- [ ] Require conversation resolution before merging.
- [ ] Require status checks to pass.
- [ ] Require branches to be up to date before merging, если CI не слишком дорогой.
- [ ] Require signed commits.
- [ ] Require deployments to succeed before merging — только для проектов с staging.
- [ ] Bypass list: только `Onmaynec`; режим Always allow либо For pull requests only в зависимости от доступных вариантов.
- [ ] Каждый bypass документировать в PR/Issue.

Обязательные checks следует назвать стабильно, например:

- `build`;
- `test`;
- `lint`;
- `format`;
- `dependency-review`;
- `secret-scan`;
- `security-scan`.

## J. Ruleset для `develop`

- [ ] Require Pull Request.
- [ ] Block force pushes and deletion.
- [ ] Require signed commits.
- [ ] Require applicable build/test/lint/format checks.
- [ ] Approvals: 1 для командных проектов; 0 допустимо для single-maintainer проекта.
- [ ] Require conversation resolution.
- [ ] Bypass: владелец.

## K. Rulesets для release/hotfix и тегов

- [ ] Branch pattern: `release/*` и `hotfix/*` — запрет удаления и force push, обязательный PR в защищённые ветки.
- [ ] Tag pattern: `v*` — ограничить создание/обновление/удаление участниками, не отвечающими за релиз.
- [ ] Релизный workflow должен проверять, что тег соответствует SemVer.
- [ ] Production environment должен требовать одобрение Maintainer/Administrator/Owner.

## L. Security and analysis каждого публичного репозитория

- [ ] Dependency Graph: On.
- [ ] Dependabot alerts: On.
- [ ] Dependabot security updates: On.
- [ ] Grouped security updates: при необходимости.
- [ ] Secret scanning: On, если доступно.
- [ ] Push protection: On, если доступно.
- [ ] Code scanning / CodeQL: On для поддерживаемых языков либо подключить другой SAST.
- [ ] Private vulnerability reporting: On для публичных репозиториев.
- [ ] `SECURITY.md` присутствует и контакты заполнены.
- [ ] Проверить security managers/team, если функция доступна на плане.

## M. CI minimum

- [ ] Workflow запускается на `pull_request` к `main` и `develop`.
- [ ] Отдельные jobs: build, test, lint, format-check.
- [ ] Dependency review на PR.
- [ ] Secret scan либо GitHub push protection.
- [ ] SAST/security scan для поддерживаемых стеков.
- [ ] Минимальные `permissions:` в каждом workflow.
- [ ] Не запускать непроверенный код fork PR с write token или secrets.
- [ ] Release artifacts создаются только из protected tag/branch.
- [ ] Artifact retention установлен осознанно.

## N. Лицензирование

- [ ] Каждый репозиторий получает отдельный `LICENSE`.
- [ ] Restricted/source-available проект: юридически проверить `LICENSE_TEMPLATE_RESTRICTED.md` и адаптировать.
- [ ] Настоящий open-source проект: выбрать OSI-approved лицензию и не добавлять запрет на коммерческое использование.
- [ ] Добавить copyright holder и год.
- [ ] Проверить лицензии зависимостей и скопированного кода.
- [ ] В PR template оставить обязательное принятие CLA.

## O. Issues и Discussions

- [ ] Загрузить Issue Forms.
- [ ] Создать labels: `bug`, `feature`, `documentation`, `question`, `security`, `duplicate`, `invalid`, `needs-info`, `breaking-change`.
- [ ] Создать Discussion categories: Announcements, Ideas, Q&A, General, Show and tell.
- [ ] Запретить публичную обработку security reports.
- [ ] Закрепить Discussion/README с правилами получения помощи.

## P. Релизы

- [ ] Версии в формате `vMAJOR.MINOR.PATCH`.
- [ ] Developer+ получает release permission только в назначенном проекте.
- [ ] Автоматический release workflow использует protected environment.
- [ ] Бинарники создаются CI и связаны с commit/tag.
- [ ] Срок поддержки: текущая major + предыдущая major 6 месяцев.
- [ ] End-of-support объявляется заранее.

## Q. Ручной квартальный аудит владельца

- [ ] Members и outside collaborators.
- [ ] Repository/team permissions.
- [ ] Owners и billing managers.
- [ ] PAT, deploy keys, SSH keys, GitHub Apps, OAuth Apps.
- [ ] Organization/repository/environment secrets.
- [ ] Ruleset bypass list.
- [ ] Archived и неактивные репозитории.
- [ ] Dependabot/code scanning/secret scanning alerts.
- [ ] Домены, release signing keys и recovery codes.

## R. Архивация

- [ ] 12 месяцев без значимой активности → review статуса.
- [ ] Опубликовать notice минимум за 30 дней.
- [ ] Указать последнюю рекомендуемую версию и известные проблемы.
- [ ] Закрыть или перенести Issues/Discussions.
- [ ] Отозвать secrets, deploy keys и release workflows.
- [ ] При разрешении community fork — явно предоставить письменное разрешение и запретить использование бренда.
- [ ] Архивировать может только владелец.
