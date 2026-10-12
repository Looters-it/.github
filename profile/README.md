# Looters

An online multiplayer conquest game played on real municipalities, Italy first and many other countries with it. Each player leads an empire: it annexes municipalities, gathers resources, builds ports and airports, makes alliances, and attacks its neighbours, turn by turn, on a real map.

## Repositories

| Repository | What is in it |
| --- | --- |
| [looters](https://github.com/Looters-it/looters) | The root: `docker-compose.yml`, shared documentation, management scripts, end-to-end tests. Start here. |
| [looters-api](https://github.com/Looters-it/looters-api) | Node.js + TypeScript, Fastify, Prisma, PostgreSQL with PostGIS. Owns the database schema and validates every action of the game. |
| [looters-jobs](https://github.com/Looters-it/looters-jobs) | Go. Background work: geographic data, turns, battle resolution from a Kafka queue. |
| [looters-web](https://github.com/Looters-it/looters-web) | React + TypeScript, Vite, Tailwind, MapLibre. The interface, in Italian and English. |

## Running it

Only Docker is needed. The three services are cloned inside the root repository:

```sh
git clone https://github.com/Looters-it/looters.git && cd looters
git clone https://github.com/Looters-it/looters-api.git api
git clone https://github.com/Looters-it/looters-jobs.git jobs
git clone https://github.com/Looters-it/looters-web.git web
cp .env.example .env      # then set ADMIN_PASSWORD (at least 12 characters)
docker compose up --build
```

The game is then at <http://localhost:8080>. Development, tests, production and backups are in the [README of the root repository](https://github.com/Looters-it/looters#readme); the technical contract between the services is in [`docs/ARCHITECTURE.md`](https://github.com/Looters-it/looters/blob/main/docs/ARCHITECTURE.md).
