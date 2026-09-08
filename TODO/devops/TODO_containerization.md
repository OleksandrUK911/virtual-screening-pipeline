# TODO — Контейнеризація (Virtual Screening)

## Dockerfile
- [ ] Dockerfile backend (FastAPI) — **P0** | ~1h
- [ ] Dockerfile worker (Celery/RQ, з RDKit та ML-залежностями) — **P0** | ~2h
- [ ] Dockerfile frontend (React build + сервер статики) — **P1** | ~1h
- [ ] Мінімізація розміру образів (multi-stage build, легкі базові образи) — **P2** | ~2h

## docker-compose
- [ ] docker-compose.yml: сервіси backend + worker + redis + postgres + frontend — **P0** | ~2h
- [ ] Налаштування volume для персистентності даних PostgreSQL — **P1** | ~1h
- [ ] Змінні середовища (.env) для конфігурації підключень між сервісами — **P1** | ~1h
- [ ] Healthcheck для кожного сервісу в compose — **P2** | ~1h

### Примітки
- Worker-образ важчий за backend через RDKit і ML-залежності — варто розділити образи, а не використовувати один universal image.

### Залежності
- Залежить від того, що backend, worker і frontend вже запускаються локально (`backend/TODO_job_queue_pipeline.md`, `frontend/TODO_pages_flows.md`).
- `devops/TODO_cicd.md` та `devops/TODO_infrastructure_deployment.md` залежать від образів, зібраних тут.
