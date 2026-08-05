# Вклад в проекты Veilbyte / Contributing to Veilbyte

## Русский

Спасибо за интерес к Veilbyte. Перед началом убедитесь, что репозиторий принимает внешние изменения и прочитайте его `README.md`, `LICENSE`, `SECURITY.md` и локальные правила.

### 1. Что можно отправлять

- исправления ошибок;
- новые функции, заранее согласованные через Issue или Discussion;
- улучшения документации;
- тесты, линтеры и улучшения CI;
- изменения производительности и безопасности.

Уязвимости нельзя отправлять через публичный Issue или обычный PR. Используйте `SECURITY.md`.

### 2. Процесс

1. Создайте или найдите Issue, если изменение не является очевидной мелкой правкой.
2. Для публичного репозитория создайте fork либо рабочую ветку, если вам выдан доступ.
3. Используйте ветки `feature/*`, `fix/*`, `release/*` или `hotfix/*`.
4. Делайте небольшие логически завершённые коммиты.
5. Подписывайте коммиты так, чтобы GitHub показывал статус Verified.
6. Используйте Conventional Commits с русским описанием: `feat: добавлена ...`.
7. Добавьте или обновите тесты и документацию.
8. Запустите локальные проверки проекта.
9. Откройте Pull Request и заполните шаблон полностью.
10. Устраните замечания review и дождитесь обязательных проверок.

### 3. Требования к коду

- код должен быть понятным и поддерживаемым;
- форматирование и линтеры проекта обязательны;
- новые зависимости должны быть обоснованы;
- секреты, персональные данные и реальные приватные логи запрещены;
- нельзя добавлять код, права на который вам не принадлежат;
- копирование из проектов с несовместимой лицензией запрещено;
- AI-код разрешён только после проверки, тестирования и понимания автором.

### 4. Лицензионные условия вклада

Отправляя Pull Request, вы подтверждаете, что имеете право предоставить код и принимаете `CONTRIBUTOR_LICENSE_AGREEMENT.md`. Вы сохраняете авторство, но предоставляете владельцу Veilbyte права, необходимые для использования, изменения, распространения, коммерциализации и перелицензирования вклада в составе проекта.

Pull Request без подтверждения CLA может быть отклонён.

### 5. Review и merge

- стандартное изменение: обычно 1 одобрение;
- критичная безопасность, криптография, сеть, updater, build/release: обычно 2 одобрения;
- single-maintainer проект может разрешить self-review через PR после CI;
- `squash merge` используется для обычных feature/fix;
- `merge commit` — для release/hotfix или сохранения истории.

### 6. Поведение

Участие означает согласие с `CODE_OF_CONDUCT.md`. Обсуждайте код, а не личность автора. Критика должна быть конкретной и применимой.

## English

Thank you for contributing to Veilbyte. Before starting, confirm that the repository accepts external contributions and read its `README.md`, `LICENSE`, `SECURITY.md`, and local rules.

### 1. Accepted contributions

Bug fixes, pre-discussed features, documentation, tests, CI improvements, performance work, and security hardening are welcome. Vulnerabilities must not be submitted through public Issues or normal PRs; follow `SECURITY.md`.

### 2. Workflow

1. Open or reference an Issue unless the change is an obvious minor edit.
2. Use a fork or an authorized working branch.
3. Use `feature/*`, `fix/*`, `release/*`, or `hotfix/*`.
4. Keep commits small and coherent.
5. Sign commits so GitHub shows Verified status.
6. Use Conventional Commits with a Russian description.
7. Add or update tests and documentation.
8. Run local project checks.
9. Open a Pull Request and complete the template.
10. Address review feedback and wait for required checks.

### 3. Code requirements

Code must be maintainable, formatted, linted, tested, free from secrets or personal data, and legally contributeable. Incompatible copied code is prohibited. AI-generated code is accepted only after the author understands, verifies, and tests it.

### 4. Contribution licensing

By submitting a Pull Request, you represent that you have the right to provide the contribution and accept `CONTRIBUTOR_LICENSE_AGREEMENT.md`. You retain authorship while granting the Veilbyte owner the rights needed to use, modify, distribute, commercialize, and relicense the contribution as part of the project.

### 5. Review and merge

Standard changes normally require one approval. Security-critical, cryptographic, networking, updater, build, and release changes normally require two. Single-maintainer repositories may self-review through a PR after CI. Squash merge is the default for ordinary features/fixes; merge commits are used for releases, hotfixes, or preserved history.

### 6. Conduct

Participation constitutes acceptance of `CODE_OF_CONDUCT.md`. Review the code, not the person. Feedback must be specific and actionable.
