# go-microservices-store/auth-service/Makefile

include .env
DB_URL=postgres://$(DB_USER):$(DB_PASSWORD)@$(DB_HOST):$(DB_PORT)/$(DB_NAME)?sslmode=$(DB_SSL_MODE)
MIGRATIONS_PATH=./db/migrations

# make migrate-create name=create_users_table
migrate-create:
	migrate create -ext sql -dir $(MIGRATIONS_PATH) -seq $(name)


migrate-up:
	migrate -path $(MIGRATIONS_PATH) -database "$(DB_URL)" up


migrate-down:
	migrate -path $(MIGRATIONS_PATH) -database "$(DB_URL)" down 1


migrate-reset:
	migrate -path $(MIGRATIONS_PATH) -database "$(DB_URL)" down
	migrate -path $(MIGRATIONS_PATH) -database "$(DB_URL)" up


migrate-version:
	migrate -path $(MIGRATIONS_PATH) -database "$(DB_URL)" version


migrate-force:
	migrate -path $(MIGRATIONS_PATH) -database "$(DB_URL)" force $(version)