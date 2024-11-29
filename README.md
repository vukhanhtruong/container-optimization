# Slimming Down a React Docker Image from 1.1 GB to 9 MB

Welcome to the repository for optimizing Docker images of a React application. In this project, we'll show you how to build and slim down a Docker image from **1.1 GB** to just **9 MB** using **multi-stage builds** and **docker-slim**.

## Table of Contents

- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Setup](#setup)
- [Building the Docker Image](#building-the-docker-image)
- [Optimizing with Docker-Slim](#optimizing-with-docker-slim)
- [Exploring with Dive](#exploring-with-dive)
- [Links](#links)

## Introduction

This project demonstrates how to bootstrap a React app using **Vite**, build a Docker image with **multi-stage builds**, and optimize it using **docker-slim**. By following these steps, you'll be able to create highly efficient Docker images, reducing size, improving deployment speed, and saving on cloud costs.

For a detailed walkthrough, check out the original post: [How I Slimmed Down My Docker Image from 1.1 GB to 9 MB](https://hihoay.substack.com/p/ed35f96c-5ae5-4528-b06a-7b9c4e873abd).

## Prerequisites

Make sure you have the following installed:

1. **Docker**: Install it from [Docker's official site](https://www.docker.com/get-started).
2. **Node.js and npm**: Get them from [Node.js](https://nodejs.org/).
3. **Slim**: Instructions available on [docker-slim's GitHub page](https://github.com/slimtoolkit/slim).
4. **Dive**: Optional, but recommended for analyzing Docker images. Install it from [Dive's GitHub page](https://github.com/wagoodman/dive).

## Setup

1. Clone this repository:

   ```sh
   git clone <repository-url>
   cd <repository-folder>
   ```

2. Install dependencies:
   ```sh
   cd container-optimization
   npm install
   ```

## Building the Docker Image

```sh
docker build -t my-app:latest .
```

The resulting image is around **54 MB**.

## Optimizing with Docker-Slim

To reduce the image size even further, use **docker-slim**:

```sh
slim build my-app:latest
```

After running docker-slim, the image size drops to just **9 MB**.

## Exploring with Dive

To inspect the Docker image and see where you can optimize further, use **Dive**:

```sh
dive my-app
```

Before running slim, the efficiency score was **88%**, with **12 MB** of potential wasted space. After slimming, Dive showed an efficiency score of **100%** with no wasted space.
