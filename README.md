# holbertonschool-softy-pinko-docker

## Docker: A Detailed Introduction

Docker is a platform that allows you to "containerize" applications, meaning you can package them into portable, self-contained environments that can run anywhere. This eliminates concerns about dependencies or configuration issues when moving your application from one environment to another, such as from your local computer to a server. Docker achieves this by using containers, which are isolated environments that contain everything an application needs to run, including libraries, dependencies, and configurations.

## Benefits of Docker
Portability: By packaging your application in a Docker container, you can easily move it between different environments without worrying about compatibility or configuration issues.

Lightweight: Docker containers are lightweight and can be started and stopped quickly, making them ideal for modern software development and deployment.

Scalability: Docker allows you to scale your application by running multiple containers of the same application on different hosts or on the same host.

## Docker Project: Infrastructure with Reverse Proxy and Load Balancing
In the project you are working on, you will create an infrastructure for an application that includes:

A reverse proxy server: This server acts as the entry point to the application, managing traffic routing to the correct servers (either the API servers or the static content server).

A load balancer: This component distributes requests between two API servers using a load balancing algorithm called "Round Robin."

Two application servers (API servers): These servers handle requests to the application's API.

A static content server (front-end server): This server handles the static content (like HTML, CSS, JS) displayed to the user.

## Function of the Reverse Proxy Server
When a request reaches the application:

Routing to the Static Content Server: If the request needs to go to the static content server, the reverse proxy will send it there. The static content returned is then sent to the client via the proxy, without the client directly communicating with the static content server.

Routing to the API Server: If the request needs to go to the API server, it first passes through a load balancer, which determines which API server to send the request to. The selected API server then responds to the proxy, which finally sends the response to the client.

## Round Robin Load Balancing
Round Robin is a simple method of distributing traffic evenly across multiple servers. In this algorithm:

If you have three servers, A, B, and C:
The first request goes to server A.
The second request goes to server B.
The third request goes to server C.
The fourth request goes back to server A, and so on.
This ensures that each server receives an equal share of the traffic, preventing any single server from becoming overwhelmed. Although it's a simple method, it's useful for applications with consistent workloads, as in this project.

## What You Need Before Starting
Install Docker Desktop on your local computer.

Docker Desktop provides everything you need to start using Docker and is compatible with Windows, Mac, and Linux.
Familiarize Yourself with Docker: If you're new to Docker, it's recommended that you go through some tutorials to understand basic concepts such as creating containers, Docker images, and running applications within these containers.
