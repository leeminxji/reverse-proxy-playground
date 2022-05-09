IMAGE_TAG:=svelte01
CONTAINER_NAME:=svelte01
DOCKERFILE:=docker/Dockerfile
PORT:=8881

build: ## Build docker image
	docker build \
		-f $(DOCKERFILE) \
		-t $(IMAGE_TAG) .
.PHONY: build

run: ## Run docker container
	docker run \
		-p $(PORT):8080 \
		-d --rm \
		--name $(CONTAINER_NAME) \
		$(IMAGE_TAG)
.PHONY: run

help: ## Show this help
	@grep -E '^[a-zA-Z_-]+:.*?## .*$$' $(MAKEFILE_LIST) | sort | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-30s\033[0m %s\n", $$1, $$2}'
.PHONY: help

.DEFAULT_GOAL := help