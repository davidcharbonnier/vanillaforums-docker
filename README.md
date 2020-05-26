# VanillaForums Docker

## Prerequisites

You need to have the following software installed on your system prior to launching this stack:

- docker-ce
- docker-compose

## Launching the stack

In order to build Docker images and launch the stack:

```bash
docker-compose up -d --build
```

Then, the application will listen on port 80 on the local machine where the stack was run: http://127.0.0.1

If you need to check for the stack's logs:

```bash
docker-compose logs -f
```

## Scaling the app component

Haproxy has a dynamic configuration based on Docker internal DNS service to be able to discover backend servers.
Currently, is has a maximum value of 10 instances of app component.

To scale the app component (here with 3 replicas):

```bash
docker-compose up -d --scale app=3
```

Application is available at the same address, Haproxy is dynamically configured to adapt to the correct number of backend servers (with a maximum of 10).

## Known issues / improvements

Here is a list of future enhancements and what could be fixed:

- we miss a way to declare a dynamic pool of Haproxy backend servers to avoid seeing 9 backends down out of 10 and be able to scale to more than 10 backend servers
