# drone pipeline template for services
In this directory you'll find some very basic examples of how to configure a drone pipeline to:
- push a latest build to docker hub on every push to master
- verify pull requests with a docker build dry run
- build and push a tagged build to docker hub when a tag is pushed

You could also combine these in a single pipeline with conditional steps, but that's not what we went for here.

The pipeline uses the [docker plugin](http://plugins.drone.io/drone-plugins/drone-docker/), by default it will use the same repository name on docker hub as on github. It uses the `DRONE_REPO` [pipeline param](https://docs.drone.io/pipeline/environment/reference/) for that. If you this should be different, you have several options:

1. hardcode the correct repository in every pipeline
2. use drone's [string operations](https://docs.drone.io/pipeline/environment/substitution/) to modify the parameter

This pipeline will alter the name of the service to strip -service in the docker hub build.  The -service postfix used on the Git forge is not relevant in the stack where each microservice is a service.  Do remove this stripping for existing services.

This pipeline will also rename the organization on the Git forge if it's redpencilio and change it to redpencil.  This is matching to our usernames on both GitHub and Docker Hub.
