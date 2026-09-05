# ASII Tajikistan — 10-Minute Institutional Demo Script

## Цель demo

За 10 минут показать не «что умеет AI», а одну институциональную способность:

> ASII сохраняет evidence lineage и decision context так, чтобы расследование можно было продолжить и проверить спустя время без потери оснований предыдущих человеческих решений.

Использовать только synthetic scenario. Не демонстрировать реальные KYC/KYB, платежные данные, live investigations, production credentials или несанкционированные institution materials.

---

## 00:00–01:00 — Problem / framing

**Показать:** краткий экран case overview или статическую architecture slide.

**Narrative:**

Финансовая организация уже получает множество сигналов из transaction monitoring, sanctions, KYC/KYB, adverse media и других систем. Проблема возникает, когда расследование проходит между системами, людьми и временем: источник сигнала остаётся в одном месте, evidence — в другом, reasoning — в notes, а final disposition сохраняется без полного decision context.

ASII не заменяет эти системы. Он демонстрируется как continuity layer между сигналом, evidence, human review и итоговым reviewable output.

**Не говорить:** «ASII уже используется банками», «регулятор одобрил», «автоматически решает AML cases».

---

## 01:00–03:00 — Signal → Case Context

**Показать:** synthetic signal и создание/открытие case.

Демонстрационный пример:

- synthetic transaction-monitoring alert;
- synthetic entity A и counterparty B;
- source timestamp;
- источник/идентификатор сигнала;
- исходный risk/context note.

**Ключевой вопрос evaluator:**

> Можем ли мы позднее однозначно восстановить, с какого сигнала началось расследование и какой контекст был доступен в тот момент?

**Контроль:** source fact отделён от последующих inference/assessment.

---

## 03:00–05:00 — Evidence → Timeline

**Показать:** добавление 2–3 synthetic evidence items.

Например:

1. synthetic KYC profile extract;
2. synthetic transaction relationship;
3. synthetic public-source/regulatory signal.

Для каждого показать:

- provenance/source reference;
- time added/observed;
- actor/action;
- связь с case/entity;
- material update в timeline.

После этого добавить новое synthetic evidence, которое меняет рабочую гипотезу.

**Главный proof:** старое состояние не исчезает. Видно, что было известно **до** нового evidence и что появилось **после**.

---

## 05:00–07:00 — Analyst Assessment → Human Review

**Показать:** analyst assessment, unresolved questions и reviewer action.

Структура:

- known facts;
- working hypothesis;
- contradictory evidence;
- unresolved questions;
- analyst recommendation;
- reviewer comments;
- human disposition + rationale.

Если используется model-assisted summary, явно маркировать его как generated/assisted material.

**Контроль:** generated text не является evidence и не является final regulated decision.

**Главный вопрос:**

> Может ли reviewer понять, на чём основана recommendation, и изменить/отклонить её с фиксированным rationale?

---

## 07:00–09:00 — Decision Context → Regulator-ready Output

**Показать:** structured output / investigation summary.

Output должен ссылаться обратно на:

- source signal;
- material evidence;
- chronology;
- analyst assessment;
- human review;
- final disposition;
- unresolved caveats where applicable.

Не представлять документ как автоматически поданный regulatory report.

**Narrative:**

ASII готовит reviewable regulator-ready material. Уполномоченный сотрудник остаётся ответственным за проверку, утверждение и любое внешнее использование.

---

## 09:00–10:00 — Continuity Proof + Ask

**Показать:** повторно открыть case в режиме другого reviewer / спустя условное время.

За 30–45 секунд ответить из системы:

- что было известно в начале;
- какой evidence появился позже;
- что изменило assessment;
- кто выполнил review;
- какое решение было принято;
- почему оно было принято;
- какая версия output была сформирована.

**Закрывающий ask:**

> Мы не предлагаем на этой встрече production rollout. Есть ли один workflow, который ваша команда считает подходящим для ограниченного synthetic technical evaluation, и кого со стороны Compliance/AML и Technology/Security следует включить в следующий review?

---

## Demo pass/fail checklist

### PASS

- synthetic data only;
- provenance visible;
- timeline reconstructable;
- previous decision context preserved;
- generated material distinguishable from source evidence;
- accountable human review visible;
- output traceable back to evidence;
- no production credentials/data;
- ask ведёт к concrete next-stage owner/team.

### FAIL / stop

- demo требует live customer data;
- невозможно объяснить происхождение evidence;
- generated output выдаётся за доказательство;
- final disposition выглядит автономным;
- historical state silently overwritten;
- security/deployment defect мешает credible demonstration;
- presenter начинает заявлять неподтверждённые customer/regulator claims.

## Evidence to capture after meeting

- дата и организация;
- участники и роли;
- показанный use case;
- заданные technical/security questions;
- objections/gaps;
- requested documents;
- identified owner/team;
- agreed next step;
- официальный follow-up artifact/link/message reference.

Встреча без следующего stage-transition evidence не считается целевым результатом September gate.
