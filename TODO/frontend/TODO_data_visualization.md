# TODO — Візуалізація даних (Virtual Screening)

## Funnel chart
- [ ] Компонент funnel chart бібліотеки/підходу з покроковими кількостями на кожній стадії (100k → 10k → 1.2k → 150 → 20) — **P0** | ~3h
- [ ] Анімовані переходи funnel chart при оновленні даних job (плавна зміна розмірів стадій замість миттєвого стрибка) — **P2** | ~2h

## Real-time прогрес job
- [ ] Компонент real-time індикатора прогресу job на основі polling (з закладеною можливістю апгрейду на WebSocket) — **P0** | ~2h
- [ ] Відображення поточної стадії пайплайну (preprocessing / fingerprints / scoring / ranking) в індикаторі прогресу — **P1** | ~2h

## Таблиця top-hits
- [ ] Таблиця результатів top-N з inline 2D-рендером структур молекул (SMILES → зображення) — **P0** | ~4h
- [ ] Ледаче завантаження (lazy loading) 2D-структур у таблиці для продуктивності при великих top-N — **P2** | ~2h

## Chemical diversity scatter plot
- [ ] Scatter plot хімічної різноманітності фінального списку хітів (PCA/t-SNE проекція fingerprints) — **P1** | ~3h
- [ ] Інтерактивність scatter plot (hover з деталями сполуки, клік → перехід до картки сполуки в таблиці результатів) — **P2** | ~2h

### Примітки
- Funnel-візуалізація — головний елемент дашборду, робити її максимально наочною; варто узгодити з базовим компонентом funnel з `frontend/TODO_ui_components.md`, щоб не дублювати реалізацію.
- Для рендеру 2D-структур молекул варто розглянути RDKit.js або серверний рендер PNG/SVG.
- PCA/t-SNE проекція для scatter plot може рахуватись на бекенді (важкі обчислення) і віддаватись фронтенду вже готовими координатами.

### Залежності
- Funnel chart і real-time прогрес напряму залежать від `backend/TODO_api_design.md` (`GET /screening-jobs/{id}`) та формату funnel-звіту з `ml/TODO_funnel_stats_reporting.md`.
- Scatter plot хімічної різноманітності залежить від аналізу diversity в `ml/TODO_evaluation_validation.md` (джерело координат/кластерів).
- Таблиця top-hits залежить від `backend/TODO_api_design.md` (`GET /screening-jobs/{id}/results`).
