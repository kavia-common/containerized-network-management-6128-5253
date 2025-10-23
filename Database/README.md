# Database (MongoDB)

This service is provisioned via docker-compose using the official MongoDB image.

- Port mapped: 5001 (host) -> 27017 (container)
- Default database: devicesdb (configurable via .env / docker-compose)

Persistent volume:
- mongo_data:/data/db

No schema is enforced at the database level; application validates input and ensures a unique index on devices.ip_address at backend startup.

Environment variables:
- DB_HOST=mongo
- DB_PORT=27017
- DB_NAME=devicesdb
- Optional: DB_USER, DB_PASS
- Alternative: MONGODB_URI
