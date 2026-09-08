# TODO — Virtual Screening & Ranking Pipeline

## Опис проєкту

Пайплайн для віртуального скринінгу великої бібліотеки сполук (десятки-сотні
тисяч compounds): фільтрація, обчислення молекулярних fingerprints, оцінка
схожості з референсними активними молекулами, ML-скоринг і фінальне
ранжування Top-N кандидатів. Демонструє data engineering + cheminformatics +
масштабовані обчислення + візуалізацію воронки скринінгу.

**Мета:** показати вміння обробляти великі об'єми молекулярних даних
ефективно (batch processing) і будувати зрозумілий funnel-дашборд результату.

**Статус:** 🔴 Не розпочато (черга після проєкту №3)

## Мовна політика

Продукт (UI, README, код, коментарі, API-документація) — англійською мовою
як основною. Українська — друга мова (i18n locale), опційна. TODO-плани
залишаються українською для зручності автора.

**Дорожня карта:** [ROADMAP.md](ROADMAP.md) — розбивка на 7 послідовних спринтів

## Категорії

## Data
- [Джерела даних та ліцензування](data/TODO_sources_licensing.md)
- [Пайплайн препроцесингу](data/TODO_preprocessing_pipeline.md)
- [Якість та валідація даних](data/TODO_quality_validation.md)
- [Версіонування та відтворюваність](data/TODO_versioning_reproducibility.md)

## ML
- [Схожість та скоринг](ml/TODO_similarity_scoring.md)
- [ML-модель скорингу](ml/TODO_ml_scoring_model.md)
- [Побудова воронки](ml/TODO_funnel_construction.md)
- [Пороги воронки](ml/TODO_funnel_thresholds.md)
- [Ранжування та статистика воронки](ml/TODO_funnel_stats_reporting.md)
- [Оцінка та валідація результатів](ml/TODO_evaluation_validation.md)
- [Реєстр моделей та документація](ml/TODO_model_registry.md)

## Backend
- [Дизайн API](backend/TODO_api_design.md)
- [Черга задач та пайплайн](backend/TODO_job_queue_pipeline.md)
- [База даних](backend/TODO_database.md)
- [Продуктивність та масштабування](backend/TODO_performance_scaling.md)
- [Тестування Backend](backend/TODO_testing.md)

## Frontend
- [Layout дашборду](frontend/TODO_dashboard_layout.md)
- [UI-компоненти](frontend/TODO_ui_components.md)
- [Візуалізація даних](frontend/TODO_data_visualization.md)
- [Сторінки та флоу](frontend/TODO_pages_flows.md)
- [Стан та шар даних](frontend/TODO_state_data_layer.md)
- [Інтернаціоналізація та локалізація](frontend/TODO_i18n_localization.md)
- [Експорт та звітність](frontend/TODO_export_reporting.md)
- [Тестування Frontend](frontend/TODO_testing.md)

## DevOps
- [Контейнеризація](devops/TODO_containerization.md)
- [CI/CD](devops/TODO_cicd.md)
- [Інфраструктура та деплой](devops/TODO_infrastructure_deployment.md)
- [Моніторинг та спостережуваність](devops/TODO_monitoring_observability.md)

## Загальний прогрес

| Категорія | Виконано | Всього |
|---|---|---|
| Data | 0 | 35 |
| ML | 0 | 51 |
| Backend | 0 | 44 |
| Frontend | 0 | 56 |
| DevOps | 0 | 27 |
| **Разом** | **0** | **213** |

### Примітки
- Ключовий технічний виклик — продуктивність на великих обʼємах (100k+ сполук), а не сама модель.
- Використовує fingerprint-пайплайн, напрацьований у проєкті №1.
- Job queue (Celery/RQ) — обов'язковий елемент архітектури, оскільки скринінг великих бібліотек не повинен блокувати HTTP-запит.
