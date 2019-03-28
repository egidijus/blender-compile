# These tools are made for compiling blender 2.80

## How

Install `make` and `git` on your machine and clone this repo.
Then, checkout the blender code:
```
make clone
```

Then, build the ubuntu docker image with all the dependencies for blender.
```
make build_ubuntu
```

Then, you should be able to run the container and have the blender compiled:
```
make up
```

