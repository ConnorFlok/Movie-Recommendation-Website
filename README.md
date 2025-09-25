# Movie Recommendation Website

A content-based movie recommendation website that helps users discover films using TF–IDF + cosine similarity and K-Means clustering.

## Features
- Search & typeahead
- Movie details (synopsis, genres, cast, director, posters)
- Similar-title recommendations
- Cluster-based discovery feeds
- Watchlist / Seen with thumbs up/down
- Admin refresh & utilization report

## Architecture
- ETL ingestion from TMDb -> PostgreSQL
- Feature pipeline (TF–IDF, cosine, K-Means) -> persisted artifacts
- FastAPI backend (search, similar, clusters, admin)
- React (or Jinja) frontend
- Docker Compose for local dev

## API (sample)
- `GET /search?q=Inception`
- `GET /movie/{id}`
- `GET /similar/{id}`
- `GET /clusters/{id}`
- `POST /admin/refresh`

## Local Setup
1. Create `.env` from `.env.example` and set `TMDB_API_KEY`.
2. `docker compose up -d db`
3. `alembic upgrade head`
4. `uvicorn app.main:app --reload`
5. (Optional) `npm run dev` for React frontend

## Tech Stack
Python 3.11, FastAPI, SQLAlchemy 2.0, Alembic, PostgreSQL, scikit-learn, pandas, React+Vite

## License
MIT
