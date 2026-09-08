# ROADMAP — Virtual Screening & Ranking Pipeline

План послідовних спринтів для одного розробника (part-time, ~1 тиждень на спринт). Кожен спринт спирається на результат попереднього — порядок важливий, особливо там, де є явні залежності між категоріями (позначені у файлах `### Залежності`).

## Sprint 1 — Дані: джерела, препроцесинг, якість
**Мета:** отримати чисту, відфільтровану, версійовану бібліотеку сполук з fingerprints, готову для скорингу.
- [Джерела даних та ліцензування](data/TODO_sources_licensing.md) (P0)
- [Пайплайн препроцесингу](data/TODO_preprocessing_pipeline.md) (P0)
- [Якість та валідація даних](data/TODO_quality_validation.md) (P0/P1 частини)
- [Версіонування та відтворюваність](data/TODO_versioning_reproducibility.md) (P0 частини: конфіг, run_id)

**Тривалість:** ~1 тиждень

## Sprint 2 — Similarity, ML-скоринг та воронка
**Мета:** порахувати similarity- та ML-скор для кожної сполуки, зафіксувати комбінований скор і пороги воронки.
- [Схожість та скоринг](ml/TODO_similarity_scoring.md) (P0)
- [ML-модель скорингу](ml/TODO_ml_scoring_model.md) (P0/P1)
- [Побудова воронки](ml/TODO_funnel_construction.md) (P0)
- [Пороги воронки](ml/TODO_funnel_thresholds.md) (P0)
- [Ранжування та статистика воронки](ml/TODO_funnel_stats_reporting.md) (P0)

**Тривалість:** ~1 тиждень

## Sprint 3 — Backend: API, база даних, job queue
**Мета:** підняти FastAPI + PostgreSQL + Celery/RQ так, щоб скринінг запускався асинхронно й прогрес по стадіях зберігався в БД.
- [Дизайн API](backend/TODO_api_design.md) (P0)
- [База даних](backend/TODO_database.md) (P0)
- [Черга задач та пайплайн](backend/TODO_job_queue_pipeline.md) (P0)

**Тривалість:** ~1 тиждень

## Sprint 4 — Продуктивність, backend-тестування
**Мета:** переконатися, що пайплайн витримує 50k-100k сполук у прийнятний час і покритий тестами.
- [Продуктивність та масштабування](backend/TODO_performance_scaling.md) (P0)
- [Тестування Backend](backend/TODO_testing.md) (P0)

**Тривалість:** ~0.5-1 тиждень

## Sprint 5 — Frontend: дашборд, флоу, стан
**Мета:** побудувати UI запуску job, funnel-візуалізацію та сторінку результатів з живим опитуванням статусу.
- [UI-компоненти](frontend/TODO_ui_components.md) (P0)
- [Стан та шар даних](frontend/TODO_state_data_layer.md) (P0)
- [Сторінки та флоу](frontend/TODO_pages_flows.md) (P0)

**Тривалість:** ~1 тиждень

## Sprint 6 — DevOps: контейнеризація, CI/CD, деплой
**Мета:** контейнеризувати всі сервіси, налаштувати CI на sample-датасеті та задеплоїти demo-версію.
- [Контейнеризація](devops/TODO_containerization.md) (P0)
- [CI/CD](devops/TODO_cicd.md) (P0/P1)
- [Інфраструктура та деплой](devops/TODO_infrastructure_deployment.md) (P0/P1)

**Тривалість:** ~1 тиждень

## Sprint 7 — Полірування: evaluation, реєстр моделей, експорт, моніторинг, frontend-тести
**Мета:** додати наукову валідацію результатів (enrichment/recovery), документацію методології, експорт/звітність, базовий моніторинг і завершити тестове покриття фронтенду.
- [Оцінка та валідація результатів](ml/TODO_evaluation_validation.md) (P0/P1)
- [Реєстр моделей та документація](ml/TODO_model_registry.md) (P1)
- [Експорт та звітність](frontend/TODO_export_reporting.md) (P1/P2)
- [Тестування Frontend](frontend/TODO_testing.md) (P0/P1)
- [Моніторинг та спостережуваність](devops/TODO_monitoring_observability.md) (P1/P2)

**Тривалість:** ~1 тиждень

---

### Загальна тривалість
~6.5-7 тижнів part-time роботи одного розробника з асистуванням Claude Code.

### Критичний шлях (P0)
Sprint 1 → Sprint 2 → Sprint 3 → Sprint 5 (frontend не може показати funnel без backend job status API) → Sprint 4 і Sprint 6 можуть частково йти паралельно з Sprint 5, якщо є час; Sprint 7 — фінальне полірування перед публікацією портфоліо.
