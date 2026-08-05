# Политика безопасности Veilbyte / Veilbyte Security Policy

## Русский

### Поддерживаемые версии

По умолчанию security-исправления предоставляются для текущей стабильной major-версии и, по возможности, для предыдущей major-версии в течение 6 месяцев после выхода новой. Конкретный репозиторий может установить другой срок.

### Как сообщить об уязвимости

Не создавайте публичный Issue, Discussion или Pull Request.

Используйте один из приватных каналов:

1. **GitHub Private Vulnerability Reporting** в разделе Security соответствующего публичного репозитория.

Дополнительные приватные контакты будут опубликованы после их официального создания.

В сообщении укажите:

- репозиторий, компонент и версию;
- тип и предполагаемую серьёзность проблемы;
- условия и шаги воспроизведения;
- минимальный proof of concept без чужих данных;
- возможное влияние;
- известные способы снижения риска;
- предпочтительный способ связи и имя для благодарности, если оно нужно.

### Сроки

Veilbyte стремится:

- подтвердить получение корректного сообщения в течение 72 часов;
- сообщить первичную оценку после воспроизведения;
- поддерживать разумную связь до исправления;
- согласовать публикацию после выпуска исправления.

Срок исправления не гарантируется и зависит от серьёзности, воспроизводимости и доступных ресурсов.

### Safe harbor

Veilbyte считает исследование добросовестным, если исследователь:

- действует только в пределах собственных аккаунтов и данных;
- использует минимальный объём тестирования;
- не нарушает доступность сервиса;
- не применяет социальную инженерию;
- не закрепляется в системах;
- не извлекает, не изменяет и не публикует чужие данные;
- прекращает тестирование после подтверждения проблемы;
- сохраняет сведения в тайне до согласованного раскрытия.

Не разрешаются DoS/DDoS, фишинг, физические атаки, спам, подбор паролей, массовое сканирование сторонней инфраструктуры, доступ к чужим аккаунтам и использование уязвимости для выгоды или давления.

### Публичное раскрытие

Исследователь может опубликовать информацию после исправления и согласования даты либо после отдельного письменного разрешения. Veilbyte может поблагодарить исследователя, если тот согласен.

### Чувствительные данные

Никогда не публикуйте токены, пароли, приватные ключи, cookies, персональные данные, полные сетевые дампы или логи без очистки.

## English

### Supported versions

By default, security fixes target the current stable major version and, on a best-effort basis, the previous major version for six months after a new major release. A repository may define a different window.

### Reporting a vulnerability

Do not create a public Issue, Discussion, or normal Pull Request. Use:

1. GitHub Private Vulnerability Reporting for the affected public repository.

Additional private contacts will be published after they are officially created.

Include the repository, component, version, vulnerability type, reproduction steps, a minimal proof of concept without third-party data, impact, mitigations, and preferred contact details.

Veilbyte aims to acknowledge a valid report within 72 hours, provide an initial assessment after reproduction, maintain reasonable communication, and coordinate disclosure after a fix. Fix timelines are not guaranteed.

Good-faith research must stay within the researcher's own accounts and data, minimize testing, preserve availability, avoid social engineering and persistence, avoid third-party data, stop after confirmation, and remain confidential until coordinated disclosure.

DoS/DDoS, phishing, physical attacks, spam, password attacks, mass scanning of third-party infrastructure, access to other users' accounts, and exploit-based coercion or profit are prohibited.

Never publish tokens, passwords, private keys, cookies, personal data, full packet captures, or unsanitized logs.
