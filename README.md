# Virtual Screening & Ranking Pipeline

Screens large compound libraries (100k+ molecules): filtering, fingerprint
similarity, ML-based activity scoring, and ranking into a shortlist of top
hits, with a job-queue backend for scale.

## Status
🔴 In planning — implementation not started yet.

## Stack
- **ML:** Python, RDKit, fingerprints, XGBoost
- **Backend:** FastAPI, Celery/RQ, Redis, PostgreSQL
- **Frontend:** React, funnel/results dashboard
- **Infra:** Docker, GitHub Actions

## How it works
```
Compound library → filters → similarity + ML scoring → ranked top hits
```

## Disclaimer
Research/educational project using public compound libraries only.

## License
TBD
