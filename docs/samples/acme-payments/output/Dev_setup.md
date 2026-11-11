# Developer Setup — Acme Payments

Prereqs: Go 1.23, Docker, Terraform 1.9, kubectl, make.

Commands:
- make bootstrap
- docker compose up -d
- make test
- make run

Copy .env.example -> .env; never commit. Secrets via Vault locally.
