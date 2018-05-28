# Licensed Container
Run GitHub's Licensed in a Docker container.

## Use
To use licensed in a containerised environment, you need to mount your project root folder into the licensed container at `/srv`.

For example:
```
docker run --rm -v $(pwd):/srv/project djbingham/licensed list
```

If running from anywhere other than your project root, swap `$(pwd)` for the absolute path to the project root. Always ensure that the project root is mounted to a subfolder of `/srv` so that the Gemfile at that location will be read to find the `licensed` bundle.

## Development
Build and tag the container image for local use:
```
script/build
```

Install test dependencies:
```
script/install-deps
```

Run licensed commands:
```
script/licensed $CMD
```

To run any other containerised commands that depend on local files (e.g. to add ruby gems):
```
script/docker-run [$OPTIONS] [$IMAGE] [$CMD]
```
