# multi.0.0.2
REGISTRY_HOST=docker.io
USERNAME=softasap
NAME=$(shell basename $(PWD))

DOCKER_HELPER := $(shell dirname $(abspath $(lastword $(MAKEFILE_LIST))))/docker_helper.sh

VERSION=$(shell . $(DOCKER_HELPER) ; getVersion)
TAG=$(shell . $(DOCKER_HELPER); getTag)
VERSIONPREFIX=$(shell . $(DOCKER_HELPER); getPrefix)
REPOSITORY=$(shell . $(DOCKER_HELPER) ; getRepositoryOr $(NAME))

IMAGE=$(REGISTRY_HOST)/$(USERNAME)/$(REPOSITORY)

SHELL=/bin/bash

.PHONY: pre-build docker-build post-build build

build: pre-build docker-build post-build

push: docker-push post-push

tag_prefix_latest:
	docker tag $(IMAGE):$(VERSIONPREFIX).$(VERSION) $(IMAGE):$(VERSIONPREFIX).latest ;

pre-build:


post-build:


post-push:


docker-build: version.txt
	docker build -t $(IMAGE):$(VERSIONPREFIX).$(VERSION) .


docker-push:
	docker push $(IMAGE):$(VERSIONPREFIX).$(VERSION)
	docker push $(IMAGE):$(VERSIONPREFIX).latest
