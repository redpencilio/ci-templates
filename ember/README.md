# drone pipeline template for ember
In this directory you'll find a .drone.yml file with some basic examples of how to configure a drone pipeline:
- test: has multiple testing steps, using the shared workspace to avoid having to run npm install each time. The pipeline runs on all triggers
- build-dry-run: does a docker build dry run, it's only triggered on PRs
- push-latest-build: build the docker image and pushes it to docker hub
- release: builds a tagged docker image and pushes it to docker hub, after that publishes on npm.

These pipelines use the  [docker plugin](http://plugins.drone.io/drone-plugins/drone-docker/) and [npm plugin](http://plugins.drone.io/drone-plugins/drone-npm/). They make use of the following [secrets](https://docs.drone.io/secret/) which should be defined on the group or repository in your drone instance:
- `docker_username`
- `docker_password`
- `npm_access_token`


The pipeline uses an adapted `DRONE_REPO` [pipeline param](https://docs.drone.io/pipeline/environment/reference/) for the Docker Hub organization.  It renames redpencilio to redpencil which matches our usernames on both GitHub and Docker Hub.

If your situation is different, you have several options:

1. hardcode the correct repository in every pipeline
2. use drone's [string operations](https://docs.drone.io/pipeline/environment/substitution/) to modify the parameter
