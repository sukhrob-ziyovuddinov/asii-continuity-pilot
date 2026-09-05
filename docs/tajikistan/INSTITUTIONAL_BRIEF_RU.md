# ASII Tajikistan — Institutional Brief

## Для кого

Руководитель/руководители Compliance, AML/CFT, Financial Monitoring, Risk, расследований финансовых преступлений, IT/Digital Transformation или Information Security регулируемой финансовой организации.

## Кратко

**ASII — Continuity-Native Financial Crime Intelligence Infrastructure.**

ASII разрабатывается как инфраструктурный слой для регулируемых организаций, который помогает не терять контекст расследования при переходе между сигналами, системами, аналитиками и этапами проверки.

Основная задача ASII — сохранить в одном reviewable контуре:

- что было известно на конкретный момент времени;
- какие источники и доказательства использовались;
- как менялась рабочая гипотеза;
- какие вопросы оставались нерешёнными;
- кто выполнил анализ и проверку;
- какое решение было принято человеком и почему;
- какие новые сведения позднее изменили оценку;
- какая версия итогового материала была подготовлена.

ASII не позиционируется как автономная система принятия AML/CFT-решений и не заменяет действующие системы банка, внутренние политики, MLRO/Compliance-функцию или систему записи организации.

## Институциональная проблема

В финансовой организации уже могут существовать transaction monitoring, sanctions screening, KYC/KYB, adverse media, case management, платежные и иные системы. Однако расследование часто проходит через несколько инструментов, сотрудников и временных периодов.

Риск возникает не только в обнаружении сигнала, но и в потере **decision context**:

`Signal → Investigation → Evidence → Human Review → Decision Context → Regulator-ready Output`

Если контекст приходится восстанавливать заново, организация теряет время, происхождение доказательств, основания предыдущих решений и воспроизводимость расследования.

## Что демонстрирует ASII

Для первого институционального evaluation предлагается один ограниченный synthetic workflow:

1. поступает тестовый regulatory/transaction/financial-crime signal;
2. создаётся case и фиксируется исходный контекст;
3. связываются entity/transaction context и evidence references;
4. строится временная линия событий и изменений;
5. аналитик формирует рабочую оценку и отмечает нерешённые вопросы;
6. другой уполномоченный участник выполняет human review;
7. disposition и rationale сохраняются отдельно от source evidence;
8. формируется reviewable regulator-ready draft/output;
9. через повторное открытие case показывается, что история решения и evidence lineage сохранились.

## Почему Tajikistan — текущий evaluation track

Национальный банк Таджикистана в августе 2026 года сообщил, что третий раунд взаимной оценки национальной системы ПОД/ФТ/ФРОМП уже начался и будет продолжаться до 2027 года. В рамках процесса страна представила вопросник технического соответствия ЕАГ, а также готовит материалы по оценке эффективности на основе 11 непосредственных результатов FATF.

Это создаёт актуальный контекст для обсуждения качества governance, evidence continuity, human review и воспроизводимости финансово-мониторинговых процессов. **Это не означает, что НБТ, ЕАГ или иной орган одобряет ASII, рекомендует ASII или предъявляет требование использовать ASII.**

## Предлагаемый первый этап

**Формат:** Controlled Technical Evaluation / Controlled PoC Proposal.

**Базовая граница:**

- один согласованный use case;
- synthetic data по умолчанию;
- de-identified test data — только после отдельного институционального разрешения;
- без production write access;
- без production credentials;
- без обязательной интеграции с core banking или иными production systems;
- без автономных regulated decisions;
- с явным human review и disposition;
- с отдельно согласованными success criteria.

## Что предлагается оценить

1. **Investigation continuity** — может ли уполномоченный reviewer восстановить ход дела без ручной реконструкции из нескольких источников.
2. **Evidence lineage** — видно ли происхождение и связь каждого существенного evidence item.
3. **Decision context** — сохранено ли, что было известно, когда, кем и почему было принято решение.
4. **Human accountability** — различимы ли generated material, analyst assessment, reviewer action и final human disposition.
5. **Auditability** — можно ли восстановить последовательность material actions и версий.
6. **Reporting preparation** — может ли система сформировать reviewable structured output без представления машинной генерации как окончательного регуляторного решения.
7. **Security/data boundary** — может ли evaluation быть проведён без ненужного доступа к production systems и live regulated data.

## Что не предлагается на первом этапе

- rip-and-replace существующих AML/KYC/case-management систем;
- production integration до security/architecture approval;
- передача live customer data в внешние model providers;
- автоматическое закрытие alerts/cases;
- автоматическое определение sanctions match;
- автоматическая блокировка/разблокировка операций;
- автоматическая подача STR/SAR/иных regulatory reports;
- утверждение production readiness после одной демонстрации.

## Как выглядит успешный следующий шаг

После демонстрации успехом считается не сама встреча, а **зафиксированный institutional stage transition**:

- определён ответственный участник или команда со стороны организации;
- согласован конкретный вопрос для следующей technical/security/evaluation session;
- организация запросила или согласилась рассматривать evaluation scope, controlled PoC или pilot consideration;
- следующий шаг и владелец действия отражены в официальном follow-up.

## Предлагаемый ask на первой встрече

Не требуется принимать решение о production внедрении.

Предлагается определить **один ограниченный workflow**, который организация считает подходящим для synthetic technical evaluation, и назначить представителей Compliance/AML и Technology/Security для проверки:

- полезности continuity model;
- security/data boundaries;
- audit/evidence requirements;
- критериев перехода к следующему этапу.

## Официальные источники контекста

- National Bank of Tajikistan, Permanent Interdepartmental Commission AML/CFT/PWMD, 20 Aug 2026: https://nbt.tj/dmm/en/news/?ELEMENT_ID=641596
- National Bank of Tajikistan, preparation for the third EAG mutual evaluation round, 12 Jun 2026: https://nbt.tj/dmm/ru/news/?ELEMENT_ID=634103
- IT Park Dushanbe resident requirements and permitted activities: https://it-park.tj/tj/rezidentho/

## Claim boundary

Этот документ является proposal/evaluation material. Он не подтверждает наличие клиента, подписанного PoC, банковского pilot, regulator endorsement, security certification или production deployment.
