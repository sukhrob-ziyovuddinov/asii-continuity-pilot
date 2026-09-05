# ASII Tajikistan — Architecture One-Pager

## Архитектурный принцип

**ONE ASII CORE → additive jurisdiction layer.**

Текущий Tajikistan evaluation track не создаёт отдельную технологическую платформу и не меняет базовую модель ASII. Локальные regulatory references, terminology, language requirements и institution-specific controls подключаются как конфигурационные и governance layers.

## Institutional flow

```text
SOURCE / SIGNAL LAYER
Transaction monitoring · Sanctions · KYC/KYB · Adverse media ·
Regulatory signal · Analyst input · Approved test source
                         │
                         ▼
ASII CONTINUITY LAYER
Case context
Entity / transaction context
Evidence references + provenance
Chronological timeline
Working assessment + unresolved questions
Decision-context history
Versioned reviewable outputs
                         │
                         ▼
HUMAN CONTROL LAYER
Analyst assessment
Independent / authorized review
Human disposition + rationale
Material status transition
                         │
                         ▼
OUTPUT LAYER
Reviewable investigation summary
Evidence / decision timeline
Audit-oriented export
Regulator-ready reporting preparation
```

## Что является core ASII

### Case continuity
Case сохраняет историю существенного контекста вместо представления только текущего состояния.

### Evidence lineage
Evidence item должен иметь источник/provenance, связь с case, время добавления и attributable actor/action. Новая информация не должна молча переписывать исторический контекст.

### Timeline
Material events, изменения оценок и human-review actions упорядочиваются во времени так, чтобы другой уполномоченный сотрудник мог восстановить последовательность.

### Decision context
Сохраняется не только итоговая disposition, но и основание решения: что было известно, какие вопросы оставались открытыми и какие данные позднее изменили assessment.

### Human review
Machine-generated или model-assisted material остаётся вспомогательным. Final regulated judgement принадлежит уполномоченному человеку.

### Regulator-ready preparation
ASII может структурировать материал для отчётности и review, но не превращает generated output в автоматически утверждённый regulatory filing.

## Evaluation deployment boundary

Первый institutional evaluation не требует:

- production core-banking integration;
- production transaction-monitoring integration;
- production KYC/KYB data;
- production credentials;
- customer-impacting write access;
- autonomous sanctions/AML decisioning;
- замены institution system of record.

Начальная демонстрация использует synthetic data. Любое последующее использование institution-controlled data или test environment требует отдельного согласования security/data/legal/architecture boundaries.

## Jurisdiction layer: Tajikistan

Additive layer может содержать:

- RU institutional interface;
- минимальный TJ official layer;
- ссылки на действующие официальные источники НБТ и других компетентных органов;
- локальную terminology/configuration;
- institution-specific workflow mapping;
- approved retention/security/integration parameters;
- формат outputs, согласованный evaluator.

Jurisdiction layer **не** должен форкать core data model без доказанной необходимости.

## Systems-of-record principle

При evaluation ASII рассматривается как continuity/intelligence overlay. Авторитетная система записи для customer data, regulatory submissions, accounting/payment actions или иных production records остаётся той, которую определяет организация.

## Technical evaluation questions

1. Может ли evaluator восстановить evidence provenance и timeline?
2. Видно ли различие между source fact, generated/inferred material, analyst assessment и human disposition?
3. Сохраняется ли предыдущий decision context после появления новой информации?
4. Можно ли провести evaluation без production access и live regulated data?
5. Какие institution-specific security, hosting, retention и identity controls необходимы перед следующим этапом?

## Production gate

Успешная демонстрация не равна production readiness.

Перед production должны отдельно пройти необходимые technical, information-security, legal/regulatory, outsourcing, data-protection, procurement, resilience, integration и operational-acceptance gates конкретной организации.
