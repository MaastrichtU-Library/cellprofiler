**CellProfiler** image mirror from https://hub.docker.com/r/cellprofiler/cellprofiler

cf. Github repository: https://github.com/CellProfiler/CellProfiler

Hosted on [GitHub Container Registry](https://github.com/orgs/vemonet/packages/container/package/cellprofiler) ([ghcr.io](https://ghcr.io)) to avoid DockerHub pull limitations, and easily deploy on clusters (such as Kubernetes).

Adapted from https://github.com/vemonet/cellprofiler/actions

## Automatically updated

[![Publish Docker image](https://github.com/seunAdeks/cellprofiler/workflows/Publish%20Docker%20image/badge.svg)](https://github.com/seunAdeks/cellprofiler/actions)

The image on [ghcr.io](https://ghcr.io) is automatically updated every week (Monday at 3:00 GMT+1) by a GitHub Actions workflow to match the `latest` tag of [cellprofiler](https://hub.docker.com/_/cellprofiler) 

## Run

```bash
docker run -it -v $(pwd):/root ghcr.io/seunadeks/cellprofiler:latest
```

In the container:

* User, with `sudo` privileges: `root`
* Workspace path: `/root`

Set entrypoint to `tail -f /dev/null` to keep it hanging as a service.

```bash
docker run -it --entrypoint tail -v $(pwd):/root ghcr.io/seunadeks/cellprofiler:latest -f /dev/null
```

## Build

Feel free to edit the `Dockerfile` to install additional packages in the image.

```bash
docker build -t ghcr.io/seunadeks/cellprofiler:latest .
```

## Push

```bash
docker push ghcr.io/seunadeks/cellprofiler:latest
```

