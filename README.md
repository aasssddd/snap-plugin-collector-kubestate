# snap collector plugin - kube state
This plugin collects metrics from Kubernetes about the state of pods, nodes and deployments.

It's used in the [snap framework](http://github.com:intelsdi-x/snap).

1. [Getting Started](#getting-started)
  * [System Requirements](#system-requirements)
  * [Installation](#installation)
  * [Configuration and Usage](configuration-and-usage)
2. [Documentation](#documentation)
  * [Collected Metrics](#collected-metrics)
  * [Examples](#examples)
  * [Roadmap](#roadmap)
3. [Community Support](#community-support)
4. [Contributing](#contributing)
5. [License](#license-and-authors)
6. [Acknowledgements](#acknowledgements)

## Getting Started
### System Requirements
* [golang 1.5+](https://golang.org/dl/) (needed only for building)

### Operating systems
All OSs currently supported by snap:
* Linux/amd64
* Darwin/amd64

### Installation
#### Download kubestate plugin binary:
You can get the pre-built binaries for your OS and architecture at snap's [GitHub Releases](https://github.com/raintank/snap-plugin-collector-kubestate/releases) page.

#### To build the plugin binary:
Fork https://github.com/raintank/snap-plugin-collector-kubestate
Clone repo into `$GOPATH/src/github.com/raintank/`:

```
$ git clone https://github.com/<yourGithubID>/snap-plugin-collector-kubestate.git
```

Build the plugin by running make within the cloned repo:
```
$ make
```
This builds the plugin in `/build/rootfs/`

### Configuration and Usage
* Set up the [snap framework](https://github.com/intelsdi-x/snap/blob/master/README.md#getting-started)
* Ensure `$SNAP_PATH` is exported
`export SNAP_PATH=$GOPATH/src/github.com/intelsdi-x/snap/build`

## Documentation
There are a number of other resources you can review to learn to use this plugin:



### Collected Metrics
This plugin has the ability to gather the following metrics:

Namespace | Description (optional)
----------|-----------------------
/grafanalabs/kubestate/pod/[NAMESPACE]/[POD]/status/condition/ready | specifies if the pod is ready to serve requests
/grafanalabs/kubestate/pod/[NAMESPACE]/[POD]/status/condition/scheduled | status of the scheduling process for the pod
/grafanalabs/kubestate/pod/[NAMESPACE]/[POD]/status/phase/[PHASE]/value | Phase can be Pending, Running, Succeeded, Failed, Unknown
/grafanalabs/kubestate/pod/container/[NAMESPACE]/[POD]/[CONTAINER]/status/ready | specifies whether the container has passed its readiness probe
/grafanalabs/kubestate/pod/container/[NAMESPACE]/[POD]/[CONTAINER]/status/restarts | number of times the container has been restarted
/grafanalabs/kubestate/pod/container/[NAMESPACE]/[POD]/[CONTAINER]/status/running | value 1 if container is running else value 0
/grafanalabs/kubestate/pod/container/[NAMESPACE]/[POD]/[CONTAINER]/status/terminated | value 1 if container is terminated else value 0
/grafanalabs/kubestate/pod/container/[NAMESPACE]/[POD]/[CONTAINER]/status/waiting | value 1 if container is waiting else value 0


### Examples

### Roadmap

1. Pod metrics
2. Node metrics
3. Deployment metrics

## Community Support

This repository is one of **many** plugins in **snap**, a powerful telemetry framework. See the full project at http://github.com/intelsdi-x/snap To reach out to other users, head to the [main framework](https://github.com/intelsdi-x/snap#community-support)

## Contributing

See our recommended process in [CONTRIBUTING.md](CONTRIBUTING.md).

## License

This plugin is released under the Apache 2.0 [License](LICENSE).

## Acknowledgements

* Author: [@daniellee](https://github.com/daniellee/)