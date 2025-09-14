DATABASE_URL:=postgres://postgres:foobarbaz@localhost:5432/postgres
.PHONY: debug-dburl
debug-dburl:
# Checks the value of DATABASE_URL
	@echo [DEBUG] DATABASE_URL='$(DATABASE_URL)'

.PHONY: run-postgres
run-postgres:
	@echo Starting postgres container
	-docker run \
		--name my_postgres \
		-e POSTGRES_PASSWORD=foobarbaz \
		-v pgdata:/var/lib/postgresql/data \
		-p 5432:5432 \
		postgres:15.1-alpine


.PHONY: run-api-node
run-api-node:
	@echo Starting node api
# 	On Linux or MacOS use:
# 		cd api-node && \
# 		DATABASE_URL=${DATABASE_URL} \
# 		npm run dev

# 	# On Windows use cmd /C "set VAR=VALUE && command"
	cd api-node && cmd /C "set DATABASE_URL=$(DATABASE_URL)&&npm run dev"

.PHONY: run-api-golang
run-api-golang:
	@echo Starting golang api
# 	On Linux or MacOS use:
# 	cd api-golang && \
# 		DATABASE_URL=${DATABASE_URL} \
# 		go run main.go

# 	# On Windows use cmd /C "set VAR=VALUE && command"
		cd api-golang && cmd /C "set DATABASE_URL=$(DATABASE_URL)&&go run main.go"

.PHONY: run-client-react
run-client-react:
	@echo Starting react client
	cd client-react && \
		npm run dev
