# learn2code_containers

This repository provides development containers for the *Software Development Lecture* [learn2code](https://github.com/BenniWi/learn2code).
The containers are meant to be used e.g. as **VSCode Devcontainers** (using [GitHub Codespaces](https://docs.github.com/en/codespaces/overview), [GitPod](https://gitpod.io/), locally, or the like)

The pre-built images can be downloaded from the [learn2code dockerhub repository](https://hub.docker.com/repository/docker/benniwi/learn2code/general)

Currently the available containers are

## Base Container

The [base container](https://github.com/BenniWi/learn2code_containers/tree/main/dockerfiles/learn2code_base) defines a container which can be used for for all programming tasks during the lecture.

## Base Marp Container

The [base marp container](https://github.com/BenniWi/learn2code_containers/tree/main/dockerfiles/learn2code_base_marp) extends the [base container](https://github.com/BenniWi/learn2code_containers/tree/main/dockerfiles/learn2code_base) with a marp layer to be able to create slides

## Lecture Container

The [lecture container](https://github.com/BenniWi/learn2code_containers/tree/main/dockerfiles/learn2code_lecture) uses the [base_marp container](https://github.com/BenniWi/learn2code_containers/tree/main/dockerfiles/learn2code_base_marp) and adds everything needed to build all the lecture code and also the lecture slides.
