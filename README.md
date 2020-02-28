# These tools are made for compiling blender 2.80

## How

This is currently broken.
I will be picking up the buildbot approach.

Buildbot is blender's ci/cd tool.

I was hoping I could just lift the commands executed in make & cmake files, but sadly, I think there is more magic coming from buildbot.

Eventually the goal of this, is to take the source of blender, build it all inside docker(you don't care how), and expose the artifacts via volume mounts. As long as it works.


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

