# Usage

- [Creating a Remix Project](#creating-a-remix-project)
- [Development](#development)

## Creating a Remix Project

Create the `src` directory.

```bash
$ mkdir src
```

Build the Dockerfile.

```bash
$ docker build ./infra/app -t node:latest
```

Start the Docker container.

```bash
$ docker run --rm -w /usr/src/app --mount type=bind,src=$pwd/src,target=/usr/src/app -it [IMAGE_ID] bash
```

Create a new Remix project.

```bash
$ npx create-remix@latest
```

Stop the Docker container.

```bash
$ exit
```

Remove the Docker image.

```bash
$ docker image rm [IMAGE_ID]
```

## Development

Edit `.env` to set environment variables.

```bash
PROJECT_NAME=docker-remix
WORKING_DIR=/usr/src/app/docker-remix
```

Go to the `infra` directory.

```bash
$ cd infra
```

Build and Start Docker containers.

```bash
$ docker compose up -d --build
```

Start the development server.

```bash
$ docker compose exec app npm run dev
```

Visit http://localhost:3000 to see the Remix default page!
