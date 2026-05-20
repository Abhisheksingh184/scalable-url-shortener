# Scalable URL Shortener

A backend project built with Java, Spring Boot, Redis, PostgreSQL, and Docker.

## Goal
Build a URL shortener that can create short links and redirect users to the original URL.  
Later, I will add custom aliases, expiry, analytics, rate limiting, JWT auth, RBAC, Redis caching, OpenAPI docs, Docker, and tests.

## Core flow
- User sends a request to create a short URL.
- App stores the mapping in PostgreSQL.
- Later, Redis will cache hot URLs for faster redirects.
- When someone opens the short link, the app finds the original URL and sends a 302 redirect.

## Planned components
- API layer: receives HTTP requests
- Service layer: contains business logic
- Repository layer: talks to PostgreSQL
- Redis cache: speeds up redirect lookup
- Analytics module: tracks clicks later
- Auth module: handles login and roles later

## Request flow
```mermaid
flowchart LR
    C[Client] --> A[Spring Boot API]
    A --> P[(PostgreSQL)]
    A --> R[(Redis Cache)]
    A --> B[302 Redirect]
