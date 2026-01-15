# ft_transcendence 


**A modern, full-stack, microservices-based Pong platform.**

https://github.com/user-attachments/assets/181181f6-bf28-4b70-8534-541fcab8962a


---

## Features

- Real-time multiplayer Pong (1v1, AI, tournaments)
- User authentication, profiles, stats, and 2FA
- Matchmaking and friend system
- Tournament mode with blockchain-backed score recording (Avalanche)
- Modern frontend (Vite + TypeScript)
- Scalable, containerized backend (Node.js, Fastify, SQLite/Postgres)
- Traefik reverse proxy with HTTPS

---

## Architecture

```
ft_transcendence/
├── frontend/         # Vite app (UI, game logic)
├── services/
│   ├── gateway-service/   # API Gateway (Fastify)
│   ├── user-service/      # Users, auth, stats, 2FA
│   ├── game-service/      # Game engine, WebSocket
│   └── blockchain-service # Blockchain integration
├── shared/           # Shared types, DTOs
├── scripts/          # DevOps, setup, testing
├── docs/             # Architecture, setup, API docs
└── traefik/          # Traefik config (TLS, routing)
```

---

## Getting Started

### Prerequisites

- Node.js 20+
- Docker & Docker Compose
- npm or yarn

### Quickstart

1. **Generate .env file**
   ```bash
   make setup
   ```
2. **Install dependencies and build**
   ```bash
   make
   ```
3. **Start all services**
   ```bash
   make up
   ```

### Accessing the Frontend

- Open [https://localhost:8443](https://localhost:8443) in your browser.
- Other PCs on your network can connect using your host's IP address and port 8443 (e.g., `https://<host-ip>:8443`).

---

## Service Overview

- **Frontend**: Modern UI, game client (port 8443 via Traefik)
- **Gateway Service**: API gateway, routing, security (port 3000)
- **User Service**: User CRUD, profiles, stats, 2FA (port 3002)
- **Game Service**: Real-time Pong, WebSocket (ports 5001, 5002)
- **Blockchain Service**: Tournament score recording (optional)

---

## Development

- Each service is independent (develop/run separately)
- Hot reload supported in Docker dev setup
- Shared types/interfaces in `shared/`

### Useful Commands

- Build all: `make build`
- Start all: `make up`
- Stop all: `make down`
- Rebuild: `make red`
- Open DB shell: `make db`

---

## Docker

- Build a service:  
  `cd services/user-service && docker build -t ft_transcendence-user-service .`
- Run all:  
  `docker-compose up -d`
- Dev mode (hot reload):  
  `docker-compose -f docker-compose.dev.yml up -d`

---

## Configuration

- Each service uses its own `.env` file (see `generate_env.sh`)
- Traefik config in `traefik/`
- Database: SQLite (dev), Postgres (prod possible)

---

## Team

- [tesla33io](https://github.com/tesla33io)
- [Inzagini](https://github.com/Inzagini)
- [eschencode](https://github.com/eschencode)
- [hsirenko](https://github.com/hsirenko)
- [DamianGacic](https://github.com/DamianGacic)

## License

MIT

---

<p align="center">
  <em>42 Ft_Transcendence &copy; 2025</em>
</p>


