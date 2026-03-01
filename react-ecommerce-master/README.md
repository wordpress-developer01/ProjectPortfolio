# React Ecommerce App

Build a FULLSTACK React Ecommerce App that is fully Responsive with Stripe Payment

Video: https://www.youtube.com/watch?v=EBCdyQ_HFMo

For all related questions and discussions about this project, check out the discord: https://discord.gg/2FfPeEk2mX


## Production / Deployment helper

I added a production skeleton (Dockerfiles, docker-compose, CI workflow and .env examples) to help run and deploy this project.

Files added:

- `client/Dockerfile` — builds the frontend and serves it with nginx using `client/nginx.conf`.
- `server/Dockerfile` — builds the Node server for production.
- `docker-compose.yml` — postgres + server + client for local production-like runs.
- `.env.example`, `client/.env.example`, `server/.env.example` — example env variables.
- `.github/workflows/ci.yml` — CI: build & test both packages and (optionally) build/push Docker images.

Quick start (local):

```bash
cp .env.example .env
cp client/.env.example client/.env
cp server/.env.example server/.env
docker-compose up --build
```

Client will be available at `http://localhost` and API at `http://localhost:3000`.

Notes:
- The CI workflow expects `DOCKERHUB_USERNAME` and `DOCKERHUB_TOKEN` in GitHub Secrets to push images. Remove or adapt the push steps if you don't use Docker Hub.
- Adjust `docker-compose.yml` ports and DB settings to match your environment.

If you want, I can:

- standardize `.gitignore` for this project,
- add a small `Makefile` for common commands (`make build`, `make up`, `make test`),
- or create a `README.PRODUCTION.md` with more detailed runbook and rollback steps.

