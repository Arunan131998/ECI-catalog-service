# Catalog Service

ECI Catalog microservice providing product CRUD, search, and authoritative pricing resolution.

## Features
- Versioned API: `/v1/products`
- Product CRUD and soft delete
- Search/filtering/pagination
- Pricing resolution endpoint for Order service
- Standard error format: `code`, `message`, `correlationId`
- OpenAPI docs at `/docs`
- Metrics at `/metrics`

## Local Run
1. Ensure PostgreSQL is running and `catalog_db` exists.
2. Create `.env` from `.env.example`.
3. Run:
   - `npm install`
   - `npm start`

## Important Endpoints
- `GET /health`
- `POST /v1/products`
- `GET /v1/products?page=1&limit=10&q=shoe`
- `PATCH /v1/products/{productId}`
- `POST /v1/products/pricing/resolve`

## Kubernetes (Minikube)
Apply manifests:
- `k8s/catalog-config.yaml`
- `k8s/catalog-db.yaml`
- `k8s/catalog-service.yaml`
