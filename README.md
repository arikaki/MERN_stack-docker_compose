# A simple MERN stack application 

### Create a network for the docker containers

`docker network create net-mern`

### Build the client 

```sh
cd mern/frontend
docker build -t mern-fe .
```

### Run the client

`docker run --name=frontend --network=net-mern -d -p 5173:5173 mern-fe`

### Verify the client is running

Open your browser and type `http://localhost:5173`

### Run the mongodb container

`docker run --network=net-mern --name mongodb -d -p 27017:27017 -v ~/opt/data:/data/db mongo:latest`

### Build the server

```sh
cd mern/backend
docker build -t mern-be .
```

### Run the server

`docker run --name=backend --network=net-mern -d -p 5050:5050 mern-be`

## Using Docker Compose

`docker compose up -d`

