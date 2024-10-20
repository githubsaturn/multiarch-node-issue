# Reproducible case - multiarch issue with node 20 docker image

See https://github.com/nodejs/docker-node/issues/2155

Creating a **multiarch image** (using buildx) works fine if we're using Node 18, and it breaks when we switch to Node 20.

Works:

```
FROM node:18-alpine

RUN echo "Node 18"
RUN node -v
RUN npm -v
RUN echo "Finished Node 18"
```

Does not work:

```
FROM node:20-alpine

RUN echo "Node 20"
RUN node -v
RUN npm -v
RUN echo "Finished Node 20"
```
