# Шаблон раздела SPEC

> Этот шаблон помогает применять PREP-06. Он не создаёт нормативных требований IMXO сам по себе.

## Название раздела

**Status:** Normative

Кратко указать назначение раздела.

## Нормативные правила

Формулировать требования с явным субъектом:

```text
A reader MUST ...
A writer MUST NOT ...
A conforming object MAY ...
```

Использовать только:

```text
MUST
MUST NOT
SHOULD
SHOULD NOT
MAY
```

## Fixed Binary Layout

Если раздел описывает фиксированную физическую структуру:

```text
Offset base: ...
Units: bytes
Byte order: ...
```

| Offset | Size | Type | Field | Description |
|---:|---:|---|---|---|
| | | | | |

При необходимости добавить колонку `Condition`.

## Logical / Variable Structure

| Field | Type | Cardinality | Condition | Description |
|---|---|---|---|---|
| | | | | |

Использовать cardinality `1`, `0..1`, `0..N`, `1..N` или конкретные пределы.

## Bit / Flag Layout

| Bits | Name | Description |
|---:|---|---|
| | | |

Для reserved bits отдельно определить writer/reader behavior.

## Семантика и ограничения

Для каждого релевантного поля определить:

- значение;
- диапазон;
- единицу;
- специальные значения;
- условия присутствия;
- invalid/unsupported behavior;
- взаимодействие с неизвестными расширениями.

## Informative Note

> **Note (Informative):** ...

Не вводить здесь новое нормативное требование.

## Example

> **Example (Informative):** ...

Пример должен соответствовать нормативному тексту, но не заменять его.

## Security Considerations

Добавлять локально только если у механизма есть специфические риски.

## Privacy Considerations

Добавлять локально только если механизм создаёт специфический риск раскрытия данных.

## References

### Normative

- ...

### Informative

- ...
