# Управление и роли Veilbyte / Veilbyte Governance and Roles

## Русский

### 1. Окончательная ответственность

Владелец Veilbyte является единственным Organization Owner и имеет окончательное право решения по:

- участникам и командам;
- доступам и исключениям;
- публикации и закрытию проектов;
- передаче, удалению, архивации и изменению видимости репозиториев;
- лицензированию и коммерческим разрешениям;
- использованию бренда;
- спорным вопросам и модерации.

### 2. Роли

**Owner** — полный контроль организации. Только владелец приглашает и удаляет участников, передаёт и удаляет репозитории.

**Administrator** — управляет назначенными репозиториями, настройками, Actions и правилами, но не получает права передавать, удалять или менять видимость репозитория без владельца.

**Maintainer** — отвечает за развитие проекта, triage, roadmap, reviews и релизы в рамках назначенного репозитория.

**Developer** — разрабатывает код, управляет ветками и PR, может публиковать релизы при явном разрешении проекта.

**Reviewer** — выполняет triage и code review, но не изменяет критические настройки.

**External Contributor** — не является постоянным участником организации; работает через fork/PR или получает минимальный доступ к конкретному репозиторию.

### 3. Принцип минимальных прав

Доступ выдаётся только к тем репозиториям и функциям, которые нужны участнику. Административные права не выдаются для удобства. Организационные секреты не предоставляются всем репозиториям по умолчанию.

### 4. Приглашения и прекращение доступа

Только владелец может приглашать и удалять участников. Автоматическое снятие доступа не используется. Не реже одного раза в квартал владелец вручную проверяет участников, outside collaborators, deploy keys, GitHub Apps, Actions secrets и токены.

### 5. Решения

Повседневные технические решения принимает Maintainer проекта. Изменения архитектуры, безопасности, лицензии, обновлений, релизной инфраструктуры или публичных обещаний требуют участия владельца либо назначенного администратора. При споре окончательное решение принимает владелец.

### 6. Emergency bypass

Владелец может обойти ruleset для срочного восстановления работоспособности или устранения угрозы. После bypass необходимо:

1. создать или обновить PR/Issue;
2. описать причину;
3. запустить пропущенные проверки при первой возможности;
4. провести последующий review.

## English

### 1. Final accountability

The Veilbyte owner is the sole Organization Owner and has final authority over membership, access, exceptions, project publication, repository transfer/deletion/archival/visibility, licensing, commercial permission, brand use, disputes, and moderation.

### 2. Roles

**Owner** — full organization control. Only the owner invites or removes participants and transfers or deletes repositories.

**Administrator** — manages assigned repositories, settings, Actions, and rules, but may not transfer, delete, or change repository visibility without the owner.

**Maintainer** — owns project direction, triage, roadmap, reviews, and releases for assigned repositories.

**Developer** — develops code, manages branches and PRs, and may publish releases when explicitly authorized.

**Reviewer** — performs triage and code review without control of critical settings.

**External Contributor** — is not a permanent organization member and contributes through forks/PRs or minimal repository-specific access.

### 3. Least privilege

Access is limited to repositories and functions required for the participant's work. Administrative access is not granted for convenience. Organization secrets are not exposed to all repositories by default.

### 4. Invitations and access removal

Only the owner may invite or remove participants. Access is not revoked automatically. At least quarterly, the owner manually reviews members, outside collaborators, deploy keys, GitHub Apps, Actions secrets, and tokens.

### 5. Decisions

Routine technical decisions belong to the project Maintainer. Architecture, security, licensing, updater, release infrastructure, or public-commitment changes require owner or appointed-administrator involvement. The owner resolves final disputes.

### 6. Emergency bypass

The owner may bypass a ruleset to restore service or address an urgent threat. The bypass must later be documented, missed checks run, and the change reviewed.
