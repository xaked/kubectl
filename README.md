
# What is Kubectl?

> Kubectl is the Kubernetes command line interface.

[Overview of kubectl](https://kubernetes.io/docs/reference/kubectl/overview/)

# TL;DR

```console
$ docker run --name kubectl mikkra/kubectl:latest
```

# Get this image

The recommended way to get the Kubectl Docker Image is to pull the prebuilt image from the [Docker Hub Registry](https://hub.docker.com/r/mikkra/kubectl).

```console
$ docker pull mikkra/kubectl:latest
```

To use a specific version, you can pull a versioned tag. You can view the [list of available versions](https://hub.docker.com/r/mikkra/kubectl/tags/) in the Docker Hub Registry.

```console
$ docker pull mikkra/kubectl:[TAG]
```

If you wish, you can also build the image yourself.

```console
$ docker build -t mikkra/kubectl:latest 1.17/debian-10
```

# Configuration

## Running commands

To run commands inside this container you can use `docker run`, for example to execute `kubectl version` you can follow the example below:

```console
$ docker run --rm --name kubectl mikkra/kubectl:latest version
```

Consult the [Kubectl Reference Documentation](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands) to find the completed list of commands available.

## Loading your own configuration

It's possible to load your own configuration, which is useful if you want to connect to a remote cluster:

```console
$ docker run --rm --name kubectl -v /path/to/your/kube/config:/.kube/config mikkra/kubectl:latest
```

# Author

> This dockerfile is forked from bitnami

# License

Copyright 2020 mikkra (Mikhail K.)

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
