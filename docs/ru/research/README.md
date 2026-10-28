# Исследования IMXO

Этот каталог содержит карточки `RSCH`: проверяемые исследования существующих стандартов, форматов, технологий и практик. `RSCH` отделяет подтверждённые факты от анализа и может дать рекомендацию, но не принимает архитектурное решение IMXO.

Текущие приоритеты, зависимости и темы без назначенных идентификаторов находятся в [`research-plan.md`](../project/research-plan.md). В реестре ниже перечислены только реально созданные карточки.

## Реестр

| ID | Название | Status | Область | Связанные Q/USE | Фаза/зависимости |
|---|---|---|---|---|---|
| [RSCH-0001](RSCH-0001-container-architecture-comparison.md) | Сравнение контейнерных архитектур | `DRAFT` | Container / Physical model | Q-0001/0002; USE-0001/0002/0003/0004 | Базовое независимое |
| [RSCH-0002](RSCH-0002-safe-physical-file-updates.md) | Безопасные изменения физического файла | `DRAFT` | Storage / Recovery / Safety | Q-0002/0012/0014; USE-0002/0004 | Параллельно 0001 |
| [RSCH-0003](RSCH-0003-text-layer-models.md) | Модели текстового слоя изображения | `DRAFT` | Text / Representation | Q-0003/0006; USE-0001/0004 | Независимое |
| [RSCH-0004](RSCH-0004-object-relationships-alternative-assertions.md) | Объекты, отношения и альтернативные утверждения | `DRAFT` | Logical model / Semantics | Q-0003/0009/0014; USE-0001/0002/0003/0004 | Обзор до проектирования |
| [RSCH-0005](RSCH-0005-provenance-transformation-chains.md) | Происхождение данных и цепочки преобразований | `DRAFT` | Provenance | Q-0007/0009; USE-0001/0002/0003/0004 | Параллельно 0004/0006 |
| [RSCH-0006](RSCH-0006-integrity-consistency-trust-boundaries.md) | Целостность, согласованность и границы доверия | `DRAFT` | Integrity / Trust | Q-0007/0008/0012; USE-0002/0003/0004 | Параллельно 0005 |
| [RSCH-0007](RSCH-0007-structured-file-sanitization.md) | Санитизация структурированных файлов | `DRAFT` | Privacy / Sanitization | Q-0002/0012/0014; USE-0002/0004 | Отдельно от 0008 |
| [RSCH-0008](RSCH-0008-media-steganography-steganalysis.md) | Стеганография и пределы стеганализа | `DRAFT` | Security / Media | Q-0008/0014; USE-0002 | Независимое |
| [RSCH-0009](RSCH-0009-partial-representations-selective-extraction.md) | Частичные представления и выборочное извлечение | `DRAFT` | Logical model / Processing | Q-0003/0011/0012; USE-0003/0004 | Параллельно 0004 |
| [RSCH-0010](RSCH-0010-ai-ingestion-threats-semantic-laundering.md) | Угрозы ИИ-потребления и отмывание семантики | `DRAFT` | Security / AI consumption | Q-0007/0008/0012; USE-0003 | Независимый threat analysis |
| [RSCH-0011](RSCH-0011-ai-input-efficiency-comparison.md) | Сравнение способов подготовки изображения для ИИ | `DRAFT` | AI / Evaluation | Q-0011/0012; USE-0003 | Методика до эксперимента |
| [RSCH-0012](RSCH-0012-cv-annotation-interchange-formats.md) | Форматы обмена CV-аннотациями | `DRAFT` | Annotations / CV | Q-0003/0009; USE-0001/0003/0004 | Независимое |

Опубликованный [`USE-0004`](../use-cases/USE-0004-structured-image-editing.md) связан с существующими карточками исследований, относящимися к обычному редактированию структурированного изображения. Новое исследование и новый идентификатор для этой публикации не создавались.

## Статус пакета

Карточки созданы как постановки и ожидают review общего плана. Содержательные исследования ещё не начаты; `Установленные факты`, `Анализ` и `Вывод` не заполнены.
