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
