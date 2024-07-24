# Create node-canvas layer

## Build the image

```bash
export NODE_VERSION=20

docker build . \
    --name node-canvas \
    --platform=linux/amd64 \
    --build-arg NODE_VERSION="${NODE_VERSION}" \
    --tag node${NODE_VERSION}-canvas-layers
```

## Run the image

```bash
docker run -it --rm node${NODE_VERSION}-canvas-layers
```

## Copy the files

In the new shell you can copy the files from the docker container to your host machine.

```bash
docker cp $(docker ps -lq):/root/layers/node${NODE_VERSION}_canvas_layer.zip .
docker cp $(docker ps -lq):/root/layers/node${NODE_VERSION}_canvas_lib64_layer.zip .
```
