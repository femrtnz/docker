NAME=femrtnz/go-http-server
TAG=v1
INSTANCE=go-http-server

.PHONY: default build copy debug clean push 

default: build

build:
	docker build -t $(NAME) .

copy:
	docker create --name $(INSTANCE) $(NAME)
	docker cp $(INSTANCE):/app/main $(shell pwd)/app
	docker rm $(INSTANCE)

clean:
	docker rm $(INSTANCE)

debug:
	docker run --rm -it --name $(INSTANCE) $(NAME) /bin/bash

run:
	docker run --rm -p 80:80 --name $(INSTANCE) $(NAME)

dev:
	docker run -it --rm -p 80:80 -w /go/src/github.com/$(NAME) -v $(shell pwd)/vendor/github.com/:/go/src/github.com/ -v $(shell pwd):/go/src/github.com/$(NAME) golang:1.13-alpine

release:
	docker build -t $(NAME):$(TAG) -f Dockerfile .
	docker tag $(NAME):$(TAG) $(NAME):latest
	
push:
	docker push $(NAME):$(TAG)
	docker push $(NAME):latest
