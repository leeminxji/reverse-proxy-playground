IMAGE_TAG:=rp-nginx
CONTAINER_NAME:=rp-nginx
DOCKERFILE:=docker/Dockerfile
PORT:=8880

build: ## Build docker image
	docker build \
		-f $(DOCKERFILE) \
		-t $(IMAGE_TAG) .
.PHONY: build

run: ## Run docker container
	docker run \
		-p 80:80 \
		-d --rm \
		--name $(CONTAINER_NAME) \
		$(IMAGE_TAG)
.PHONY: run

bash: ## Enter the docker container
	docker run \
		-it --rm \
		--name $(CONTAINER_NAME) \
		$(IMAGE_TAG) \
		bash
.PHONY: bash

help: ## Show this help
	@grep -E '^[a-zA-Z_-]+:.*?## .*$$' $(MAKEFILE_LIST) | sort | awk 'BEGIN {FS = ":.*?## "}; {printf "\033[36m%-30s\033[0m %s\n", $$1, $$2}'
.PHONY: help

.DEFAULT_GOAL := help