# TODO — Схожість та скоринг (Virtual Screening)

## Обчислення similarity
- [ ] Обчислення Tanimoto similarity до референсних активних молекул на основі Morgan fingerprints — **P0** | ~2h
- [ ] Обчислення similarity на основі MACCS keys як альтернативи для порівняння — **P1** | ~1h
- [ ] Для кожної сполуки — max similarity серед усіх референсних actives (не тільки середнє) — **P0** | ~1h
- [ ] Векторизоване (bulk) обчислення similarity для великих обʼємів сполук — **P0** | ~2h

## Методи порівняння
- [ ] Порівняти Tanimoto з альтернативними метриками (Dice, Cosine) на невеликому прикладі — **P2** | ~2h
- [ ] Обрати фінальну fingerprint-метрику з обґрунтуванням у README — **P1** | ~1h

## Комбінований скор
- [ ] Формула комбінованого скору (similarity + ML-prediction) з ваговими коефіцієнтами — **P0** | ~2h
- [ ] Нормалізація компонентів скору перед комбінуванням (шкала 0-1) — **P0** | ~1h

### Примітки
- Bulk-обчислення Tanimoto (наприклад через `BulkTanimotoSimilarity` у RDKit) суттєво швидше за попарний цикл на Python.

### Залежності
- Залежить від `data/TODO_preprocessing_pipeline.md` (fingerprints) та `data/TODO_sources_licensing.md` (референсні actives).
- Формула комбінованого скору тут узгоджена з `ml/TODO_scoring_model_combination.md`-подібною логікою в `ml/TODO_ml_scoring_model.md` — обидва компоненти мають бути готові перед фіналізацією ваг.
