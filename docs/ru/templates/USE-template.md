# USE-xxxx — <краткое название сценария>

**Status:** DRAFT  
**Disposition:** CANDIDATE  
**Created:** YYYY-MM-DD  
**Updated:** YYYY-MM-DD

> `USE` является информативным описанием сценария применения. Эта карточка не является нормативным требованием, архитектурным решением или доказательством необходимости функции.

Для существенных характеристик используйте явные значения `unknown`, `to be researched`, `estimated`, `range`, `not applicable` или однозначные эквиваленты, если точные сведения пока отсутствуют.

## Actors / systems

Кто или какие системы участвуют в сценарии.

Примеры категорий: человек, ОС, приложение, камера, screenshot tool, AI agent, CV system, editor, archive, assistive technology, web service.

## Context

В каком контексте возникает задача.

Опишите только тот контекст, который необходим для понимания сценария.

## Problem / need

Какую проблему или потребность представляет сценарий.

Не фиксируйте техническое решение, если оно ещё не принято.

## Goal

Какого результата пытается добиться actor/system.

## Trigger

Что запускает сценарий.

Если отдельный trigger не нужен, раздел можно удалить.

## Scenario

Краткая последовательность событий или взаимодействий.

Не превращайте раздел в описание внутренней архитектуры IMXO.

## In scope

Что относится к этому сценарию.

## Out of scope

Что намеренно не рассматривается в этой карточке.

Это особенно важно, если рядом находятся связанные, но самостоятельные задачи.

## Inputs

Входные данные или исходные условия, если они существенны.

Если раздел неприменим, его можно удалить.

## Operational profile

- Frequency / event rate:
- Typical volume:
- Peak / burst characteristics:
- Interactive or batch:
- Producers / consumers:
- Is manual review realistic:
- Sensitivity to processing/storage overhead:

Не смешивайте global market/adoption scale с operational characteristics этого сценария.

## Longevity and verification expectations

- Expected useful lifetime:
- Expected retention period:
- Required provenance / integrity verification horizon:
- Offline or self-contained verification needed:
- Dependence on external services acceptable:

Фиксируйте ожидания сценария, не выбирая cryptographic, PKI или archival architecture.

## Expected outcome

Какой результат должен быть получен с точки зрения сценария.

## Success conditions

Наблюдаемые условия, при которых сценарий можно считать успешно выполненным.

Success conditions не являются conformance requirements и сами по себе не создают `MUST / SHOULD / MAY`.

## Failure and representation-divergence impact

- What if structured data is wrong or stale?
- What if structured and visible representations disagree?
- Who or what consumes the incorrect representation?
- Can this trigger automated action?
- Would a human notice the mismatch?
- Are the consequences reversible?
- What material harm may result?
- Which representations or layers may diverge?

Наличие злоумышленника для этого раздела не предполагается.

## Adversarial / misuse incentives

- Who could benefit from false or inconsistent data?
- What could they gain?
- What would be beneficial to falsify?
- Which representation/layer would be attractive to manipulate?
- Who or what could be misled?
- What downstream effect could result?

Не назначайте субъективные уровни угрозы или риска без отдельной принятой модели.

## Structured-data exposure and data minimization

- What sensitive data may become machine-readable?
- Is it already visible in the rendered image?
- Could structured data expose information not visible to the user?
- Can sensitive data be excluded at capture time?
- Can source/application semantics help exclude it?
- Can the data be safely removed after capture?
- What happens during redaction/sanitization?
- Which related representations must be updated together?
- What are the indexing/search risks?
- What are the AI/agent ingestion risks?
- Does machine readability, searchability, indexing, copying, AI/agent ingestion, or bulk extraction amplify exposure?

Обязательно проверьте риск расхождения вида:

```text
visible representation:
Password: ••••••••

structured representation:
Password: real-secret-value
```

Не выбирайте в этой карточке конкретный механизм защиты.

## Current workflow and known limitations

Как задача решается сейчас и какие подтверждённые ограничения известны.

Не выдавайте предположения о пользователях, рынке, regulation или adoption за установленные факты.

## Assumptions / hypotheses

Рабочие предположения, которые ещё требуют проверки.

При возможности укажите, что именно должно быть проверено будущим `RSCH`.

## Relevance to IMXO

Почему этот сценарий может быть релевантен IMXO.

Этот раздел является обоснованием исследования сценария, а не доказательством необходимости функции.

## Cross-cutting considerations

Добавляйте только релевантные подпункты.

Возможные области:

- Accessibility
- Security
- Privacy
- Trust
- IPR
- Interoperability
- Preservation / archival concerns

Не создавайте пустые подпункты только ради шаблона.

Этот раздел не заменяет основные характеристики operational profile, longevity and verification, failure/divergence, adversarial incentives и structured-data exposure.

## Open questions

Связанные неизвестности и вопросы.

При наличии существующих `Q` используйте ссылки.

## Related artifacts

### Related questions

- none

### Related research

- none

### Related requirements

- none

### Related design

- none

### Related decisions

- none

## Supersession

Если карточка не supersedes и не superseded, раздел можно удалить.

**Supersedes:** none  
**Superseded by:** none

## History

- YYYY-MM-DD — карточка создана.
