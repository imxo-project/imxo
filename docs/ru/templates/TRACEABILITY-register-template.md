# IMXO Traceability Register — шаблон

> Этот файл является шаблоном информационного инженерного артефакта. Реальный Traceability Register создаётся после появления первых требований и нормативных элементов SPEC.

## 1. Requirements traceability

| Requirement | Use cases | Questions | Research | Design | Decision | Specification |
|---|---|---|---|---|---|---|
| REQ-XXXX | USE-XXXX | Q-XXXX | RSCH-XXXX | DES-XXXX | ADR-XXXX | stable SPEC anchor |

В одной ячейке допускается несколько ссылок.

Не требуется искусственно заполнять каждый класс артефактов, если он не нужен.

## 2. Decision traceability

| Decision | Use cases | Questions | Research | Requirements | Design | Specification |
|---|---|---|---|---|---|---|
| ADR-XXXX | USE-XXXX | Q-XXXX | RSCH-XXXX | REQ-XXXX | DES-XXXX | stable SPEC anchor |

## 3. Specification backtrace

| SPEC anchor | Requirement | Decision | Use cases | Questions | Research |
|---|---|---|---|---|---|
| stable SPEC anchor | REQ-XXXX | ADR-XXXX | USE-XXXX | Q-XXXX | RSCH-XXXX |

Эта таблица обеспечивает обратную трассировку от нормативного текста к происхождению решения.

## 4. Future conformance traceability

После появления conformance tooling допускается дополнительная таблица:

| SPEC anchor / Requirement | Conformance rule | Test vector | Validator test | Status |
|---|---|---|---|---|
| | | | | |

PREP-06 не требует создавать её до появления соответствующих материалов.

## Правила

- Traceability Register является Informative.
- Он не заменяет normative SPEC.
- Many-to-many связи допустимы.
- Поля `Use cases` и `Questions` необязательны и не создаются искусственно для каждой связи.
- Ссылки по возможности используют стабильные identifiers/anchors.
- Отображаемый номер раздела не должен быть единственной точкой привязки.
- Отсутствующий промежуточный класс не создаётся только ради заполнения таблицы.
