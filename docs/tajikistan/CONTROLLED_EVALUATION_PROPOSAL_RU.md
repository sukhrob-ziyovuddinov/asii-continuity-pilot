# ASII Tajikistan — Controlled Technical Evaluation / PoC Proposal

## Статус документа

**Proposal — для обсуждения с потенциальным institutional evaluator.**

Этот документ не означает, что evaluation, PoC или pilot уже согласованы. Продолжительность, роли, среда, security controls, data classes и success criteria должны быть подтверждены конкретной организацией до начала соответствующего этапа.

## Цель

В ограниченном и контролируемом формате проверить, способен ли ASII улучшить **investigation continuity** без замены существующей технологической инфраструктуры и без необходимости использовать live production data на первом этапе.

Основной вопрос evaluation:

> Может ли другой уполномоченный reviewer через дни или недели восстановить, что было известно, какие evidence использовались, как менялась оценка, кто выполнил review и почему было принято конкретное human disposition?

## Предлагаемый use case

Один согласованный financial-crime investigation workflow, например synthetic alert / regulatory signal, проходящий через:

`Signal → Case Context → Evidence → Timeline → Analyst Assessment → Human Review → Disposition → Regulator-ready Output`

Конкретный тип use case выбирается совместно с evaluator. Для первого этапа не требуется подключение к production transaction monitoring, core banking, sanctions, KYC/KYB или regulatory filing systems.

## Предлагаемая продолжительность

**До 30 календарных дней после формального согласования scope.**

30 дней — рабочая рамка, а не обязательный срок. Организация может уменьшить или изменить период после technical/security review.

## Фазы evaluation

### Phase 0 — Scope & Control Confirmation

До начала:

- подтвердить institutional owner и technical/security counterparts;
- выбрать один use case;
- подтвердить synthetic-data boundary;
- согласовать expected outputs и success criteria;
- определить, какие evaluation artifacts могут храниться;
- зафиксировать отсутствие production write access;
- определить stop criteria и escalation route.

**Exit:** подписанный/зафиксированный evaluation scope либо письменное решение не продолжать.

### Phase 1 — Controlled Demonstration

- загрузить/создать synthetic case;
- показать source signal и provenance;
- связать entity/transaction context;
- добавить evidence items;
- построить investigation timeline;
- зафиксировать analyst assessment и unresolved questions;
- выполнить accountable human review;
- зафиксировать disposition/rationale;
- сформировать reviewable structured output.

**Exit:** evaluator подтвердил, что workflow понятен и может быть предметом дальнейшего assessment.

### Phase 2 — Evaluator-Led Test

Evaluator получает заранее согласованный synthetic scenario или собственный institution-approved test scenario.

Проверяется:

- reconstructability case history;
- evidence provenance;
- chronology;
- separation source/generated/analyst/reviewer material;
- attribution actor/time/action;
- preservation of previous decision context after new information;
- reviewability of final output.

**Exit:** evidence-backed findings list.

### Phase 3 — Security / Architecture Review

Совместно определить, что потребуется, если организация захочет перейти от synthetic evaluation к controlled PoC с institution-controlled environment/data.

Темы:

- hosting/region/tenancy;
- authentication and authorization;
- data classification;
- encryption;
- logs/audit;
- providers/subprocessors;
- retention/deletion;
- incident/vulnerability handling;
- integration boundary;
- system of record;
- rollback/exit.

**Exit:** список mandatory gates, не production approval.

### Phase 4 — Evaluation Closeout

Итоговый review:

- что было доказано;
- что не было доказано;
- defects/control gaps;
- institution-specific requirements;
- agreed owner/team;
- next-stage decision.

Возможные outcomes:

1. stop / no further action;
2. request for more evidence;
3. additional technical evaluation;
4. scoped Controlled PoC consideration;
5. pilot consideration subject to governance/security/procurement gates.

## Data boundary

### Разрешено по умолчанию

- полностью synthetic persons/entities;
- synthetic transactions;
- synthetic alerts;
- invented evidence documents/notes;
- synthetic model prompts/outputs;
- institution-approved generic policies/templates where no confidential information is exposed.

### Только после отдельного разрешения

- de-identified institution test data;
- institution-confidential workflow material;
- controlled test-environment integration.

### Не требуется и запрещено по умолчанию

- live customer KYC/KYB;
- production account/payment records;
- live sanctions investigations;
- STR/SAR or equivalent restricted case material;
- production credentials/secrets;
- unrestricted production database access.

Полная security/data boundary определена в `/SECURITY_DATA_BOUNDARY.md`.

## Roles

### Institution-side

Рекомендуемый минимальный состав:

- **Business/Control Owner:** Compliance / AML / Financial Monitoring representative;
- **Reviewer:** authorized investigator/analyst or control reviewer;
- **Technology Owner:** IT / Digital / Architecture representative;
- **Security Owner:** Information Security representative where required.

Конкретные должности назначает организация.

### ASII-side

- evaluation coordinator;
- product/technical presenter;
- technical/security contact.

Наличие этих ролей в proposal не означает существование отдельной штатной команды; фактические ответственные лица должны быть указаны до начала evaluation.

## Success criteria

Evaluation считается содержательно успешным, если evaluator на тестовом сценарии может подтвердить следующие наблюдаемые свойства:

### SC-1 — Context reconstruction
Reviewer может восстановить material history case без ручного поиска по нескольким несвязанным записям ASII.

### SC-2 — Evidence provenance
Существенный evidence item имеет идентифицируемое происхождение и связь с case.

### SC-3 — Chronology
Material events и изменения assessment представлены в воспроизводимой временной последовательности.

### SC-4 — Human accountability
Видно, кто выполнил analyst action, кто review, и какой human disposition был зафиксирован.

### SC-5 — Decision-context preservation
После появления новой информации историческое основание предыдущего решения не исчезает и не переписывается молча.

### SC-6 — Output reviewability
Structured output можно проверить против evidence/timeline до любого дальнейшего использования.

### SC-7 — Boundary compliance
Synthetic evaluation не требует production credentials, production writes или autonomous regulated action.

## Неиспользуемые критерии без измерения

До проведения реального controlled test нельзя заявлять:

- конкретный процент сокращения investigation time;
- false-positive reduction;
- cost savings;
- accuracy uplift;
- model superiority;
- SLA/availability;
- regulator acceptance.

Если evaluator считает такие метрики необходимыми, baseline, measurement method и acceptance threshold должны быть согласованы заранее.

## Stop criteria

Evaluation приостанавливается, если:

- обнаружено использование неразрешённой data class;
- требуются production secrets/access вне согласованного scope;
- выявлен material security defect, делающий продолжение небезопасным;
- система используется для autonomous regulated decision;
- отсутствует accountable owner для следующего material action;
- scope существенно меняется без повторного согласования.

## Expected artifacts

- agreed evaluation scope;
- synthetic scenario definition;
- evidence/timeline sample;
- human-review/disposition sample;
- structured regulator-ready draft sample;
- security/architecture questions register;
- evaluation findings;
- documented next-step decision.

## Governance gates после evaluation

Даже положительный evaluation result **не** означает production readiness.

Перед pilot/production могут потребоваться отдельные:

- information-security review;
- legal/regulatory review;
- data-protection review;
- vendor/outsourcing review;
- architecture/integration approval;
- procurement;
- operational resilience/BCP review;
- production acceptance and change-management approval.

## Предлагаемый decision ask

На первой substantive session организация не принимает решение о production внедрении.

Запрашивается только решение:

> Есть ли один workflow, для которого организация готова назначить owner/team и рассмотреть synthetic technical evaluation по согласованным success criteria?
