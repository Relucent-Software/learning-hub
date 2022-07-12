---
title: Docker Introduction
---

Docker refers to three main principles:

- The Docker Image
- The Docker Registry
- The Docker Container
  > The Docker Container is the most common concept referred to as "Docker"

Docker has, at one of its core concepts, an intended structure:

> ```Build -> Ship -> Run```

These are the key steps for containerising an application.

## The Docker Image

> The container image, universal app packager.

The Docker image is cross-OS, cross-platform, and cross-language.

### The Dockerfile

The dockerfile is a set of instructions to make a docker image.

An example of a simple dockerfile is as follows:

```docker
FROM python
RUN pip install flask
WORKDIR /app
COPY . .
CMD python app.py
```

> ```docker build```
>
> Turns the application and dependencies into a single container.

## The Docker Registry

> Universal app distribution

> ```docker push```
>
> Sends a built docker image to a registry.

> ```docker pull```
>
> Pulls an identical copy of an image from a registry.

:::note

Linux-based images must be built on a linux machine, or on one with access to
the linux kernel.

:::

## The Docker Container

> Identical runtime environments

> ```docker run```
>
> - Cannot access files that aren't included in the original image
> - Has its own blank filesystem
> - Has its own IP address
> - Has its own virtual NIC (Network Interface Card)

Two identical running containers cannot see eachother by default.
