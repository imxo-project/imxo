# Открытые вопросы IMXO

Этот документ является живым индексом существенных вопросов проекта, которые ещё не получили окончательного решения.

Исходные вопросы `Q-0001…Q-0012` перенесены из `PREP-00`. PREP-00 остаётся исторической контрольной точкой, а текущее состояние вопросов отслеживается здесь и в отдельных карточках. Вопрос `Q-0013` добавлен по итогам PREP-07.

## Правила

- допустимые статусы: `OPEN`, `RESOLVED`, `SUPERSEDED`;
- идентификаторы `Q-xxxx` не переиспользуются;
- после закрытия вопрос не удаляется;
- каждый существенный вопрос имеет отдельную Markdown-карточку;
- новые существенные вопросы после закрытия PREP-05 начинаются с GitHub Issue и после первичного рассмотрения при необходимости получают идентификатор `Q-xxxx`.

## Реестр

| ID | Вопрос | Статус | Область |
|---|---|---|---|
| [Q-0001](questions/Q-0001-container-architecture.md) | Контейнерная архитектура IMXO | `OPEN` | Container |
| [Q-0002](questions/Q-0002-physical-file-structure.md) | Физическая структура файла | `OPEN` | Container |
| [Q-0003](questions/Q-0003-logical-object-model.md) | Логическая объектная модель | `OPEN` | Logical model |
| [Q-0004](questions/Q-0004-identification.md) | MIME type, magic и brand | `OPEN` | Identification |
| [Q-0005](questions/Q-0005-versioning.md) | Версионирование IMXO | `OPEN` | Versioning |
| [Q-0006](questions/Q-0006-text-fonts-glyph-fallback.md) | Текст, шрифты и glyph fallback | `OPEN` | Text |
| [Q-0007](questions/Q-0007-provenance-model.md) | Provenance model | `OPEN` | Provenance |
| [Q-0008](questions/Q-0008-integrity-trust-model.md) | Integrity / Trust model | `OPEN` | Security / Trust |
| [Q-0009](questions/Q-0009-cv-annotations.md) | Computer Vision annotations | `OPEN` | Annotations / CV |
| [Q-0010](questions/Q-0010-accessibility-model.md) | Accessibility model | `OPEN` | Accessibility |
| [Q-0011](questions/Q-0011-sdk-integrations.md) | SDK и интеграции | `OPEN` | Implementation |
| [Q-0012](questions/Q-0012-conformance-model.md) | Conformance model | `OPEN` | Conformance |
| [Q-0013](questions/Q-0013-accessibility-regulatory-adoption.md) | Стандарты доступности, нормативное сопоставление и принятие формата | `OPEN` | Accessibility / Adoption / Standards mapping |

## Добавление новых вопросов

Следующий свободный идентификатор: `Q-0014`.

Новый существенный вопрос сначала оформляется через GitHub Issue. После решения maintainer о включении вопроса в формальный процесс создаётся карточка по шаблону `Q-template.md`, присваивается очередной постоянный `Q-xxxx`, а индекс обновляется.
