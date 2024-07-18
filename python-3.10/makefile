# Get the current date and time precise to the second
DATE_TAG := $(shell date +%Y-%m-%d_%H-%M-%S)

# Docker image name
IMAGE_NAME := my-image

# Default target
all: build

# Build the Docker image with the current date tag
build:
	docker build -t $(IMAGE_NAME):$(DATE_TAG) .

# Clean up the Docker image
clean:
	docker rmi $(IMAGE_NAME):$(DATE_TAG)

.PHONY: all build clean