# ci-templates

This repository holds a few examples on how to configure ci pipelines.

Currently [drone](https://www.drone.io/) and [woodpecker](https://woodpecker-ci.org/) (preferred) are supported by redpencil.


## woodpecker
- [service](woodpecker/service) holds examples for a typical service needing a build on docker hub
- [ember](woodpecker/ember) holds examples for ember frontends and addons

## drone

- [service](drone/service) holds examples for a typical service needing a build on docker hub
- [ember](drone/ember) holds examples for ember frontends and addons

When using these examples, make sure to [test them locally](https://docs.drone.io/quickstart/cli/) using `drone exec` before pushing them to your repository.

For more information see:
- [drone.io pipeline overview](https://docs.drone.io/pipeline/overview/)
- [drone.io quickstart guide](https://docs.drone.io/quickstart/docker/)
