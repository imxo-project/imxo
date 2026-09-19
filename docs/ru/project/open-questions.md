# Открытые вопросы IMXO

Этот документ является живым реестром существенных вопросов проекта, которые ещё не получили окончательного решения.

Исходные вопросы перенесены из `PREP-00`.

PREP-00 остаётся неизменяемой исторической контрольной точкой. Текущее состояние вопросов отслеживается здесь.

## Правила

Допустимые статусы:

- `OPEN`;
- `RESOLVED`;
- `SUPERSEDED`.

Идентификаторы `Q-xxxx` не переиспользуются.

После закрытия вопрос не удаляется.

## Q-0001 — Контейнерная архитектура IMXO

**Status:** OPEN  
**Area:** Container  
**Source:** PREP-00

Определить, должен ли IMXO использовать полностью собственный контейнер, профиль/надстройку над существующим контейнером или гибридный подход.

**Research:** not assigned  
**Resolution:** not resolved

## Q-0002 — Физическая структура файла

**Status:** OPEN  
**Area:** Container  
**Source:** PREP-00

Определить signature, endian, заголовки, type, size, object identifiers, flags, CRC/hashes, nesting, footer, indexes, recovery markers, padding/alignment, обработку повреждений и сохранение неизвестных блоков.

**Research:** not assigned  
**Resolution:** not resolved

## Q-0003 — Логическая объектная модель

**Status:** OPEN  
**Area:** Logical model  
**Source:** PREP-00

Определить базовые типы объектов, обязательные и необязательные сущности, отношения, идентификаторы, ссылки, вложенность, владение данными, расширения и отображение логической модели в контейнер.

**Research:** not assigned  
**Resolution:** not resolved

## Q-0004 — MIME type, magic и brand

**Status:** OPEN  
**Area:** Identification  
**Source:** PREP-00

Определить MIME type, magic bytes, возможный container brand и правила идентификации версии/профиля.

**Research:** not assigned  
**Resolution:** not resolved

## Q-0005 — Версионирование IMXO

**Status:** OPEN  
**Area:** Versioning  
**Source:** PREP-00

Определить модель версионирования формата, контейнера, логической модели, расширений, профилей и совместимости между версиями.

**Research:** not assigned  
**Resolution:** not resolved

## Q-0006 — Текст, шрифты и glyph fallback

**Status:** OPEN  
**Area:** Text  
**Source:** PREP-00

Определить встраивание шрифтов, licensing constraints, glyph raster fallback, связь отображаемого и копируемого текста, отсутствие исходного шрифта и сложные системы письма.

**Research:** not assigned  
**Resolution:** not resolved

## Q-0007 — Provenance model

**Status:** OPEN  
**Area:** Provenance  
**Source:** PREP-00

Определить структуру provenance, гранулярность, идентификацию источников, цепочки преобразований, доверенные и недоверенные источники, наследование и взаимодействие с хэшами/подписями.

**Research:** not assigned  
**Resolution:** not resolved

## Q-0008 — Integrity / Trust model

**Status:** OPEN  
**Area:** Security / Trust  
**Source:** PREP-00

Определить модель хэширования, область действия хэшей, связь визуального и структурированного представлений, признаки изменённых/неподтверждённых данных, trust indicator, частичную проверку и возможные цифровые подписи.

**Research:** not assigned  
**Resolution:** not resolved

## Q-0009 — Computer Vision annotations

**Status:** OPEN  
**Area:** Annotations / CV  
**Source:** PREP-00

Исследовать совместимость с YOLO, COCO, bounding boxes, polygons, masks, points, labels, confidence и определить границу между нормативными концепциями IMXO и отображением внешних схем.

**Research:** not assigned  
**Resolution:** not resolved

## Q-0010 — Accessibility model

**Status:** OPEN  
**Area:** Accessibility  
**Source:** PREP-00

Определить нормативную модель alt-like description, описаний изображения и областей, языковых атрибутов и связи с текстовым/семантическим слоями.

**Research:** not assigned  
**Resolution:** not resolved

## Q-0011 — SDK и интеграции

**Status:** OPEN  
**Area:** Implementation  
**Source:** PREP-00

Определить дальнейшую модель SDK, API, платформенных интеграций, viewer/editor integration, браузеров и инструментов захвата после стабилизации базовой архитектуры.

**Research:** not assigned  
**Resolution:** not resolved

## Q-0012 — Conformance model

**Status:** OPEN  
**Area:** Conformance  
**Source:** PREP-00

Определить уровни соответствия, обязательные возможности decoder/encoder, поведение при неизвестных расширениях, test suites, reference files и validation rules.

**Research:** not assigned  
**Resolution:** not resolved

## Добавление новых вопросов

Новые существенные вопросы получают очередной постоянный идентификатор: `Q-0013`, `Q-0014` и далее.
