---
layout: ../../layouts/ProjectLayout.astro
title: Greenlight API
description: A production-ready REST API in Go
tags: ["go"]
githubUrl: https://github.com/RATIU5/zaggonaut
timestamp: 2025-02-24T02:39:03+00:00
featured: true
filename: greenlight-api
---

## The Details

This is a production-ready REST API built in Go, designed with clean architecture principles and a focus on performance, maintainability, and clarity. The project includes a complete implementation of core backend features using idiomatic Go and is structured for real-world usage.

## The Features

- Clean, layered architecture (handlers, services, data access)
- JWT authentication and authorization
- PostgreSQL integration with connection pooling
- Input validation with detailed error responses
- Filtering, sorting, and pagination for list endpoints
- Rate limiting with token bucket implementationRate limiting with token bucket implementation
- Unit and integration tests using Go’s testing package
- Structured JSON logging
- Graceful shutdown for server and background workers
- Middleware system for resuavle cross-cutting logic
- Environment-based configuration via .env or flags
- Request timeout handling
- Robust error handling with custom response types

## The Future

Check out [API](https://github.com/sasirura/greenlight-api) to see it in action!
