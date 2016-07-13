# pbrt-v2-spectral-docker
Dockerfile and instructions for building [pbrt-v2-spectral](https://github.com/ydnality/pbrt-v2-spectral), a customized version of the [PBRT](http://www.pbrt.org/) renderer.

# Hi!

The `Dockerfile` in this repository represents a complete set of instructions for building pbrt-v2-spectral on Ubuntu.  You can use this to create a Docker image with PBRT in it.

You can also consult this to figure out how to build PBRT.  The RUN commands are thing you can run on the command line.  Some of them will require `sudo`.

# Get the Docker Image

This Docker image is hosted on [DockerHub](https://hub.docker.com/r/ninjaben/pbrt-v2-spectral-docker/).  You can obtain it locally with:
```
sudo docker pull ninjaben/pbrt-v2-spectral-docker
```

Or you can build it yourself from the Dockerfile:
```
git clone https://github.com/benjamin-heasly/pbrt-v2-spectral-docker.git
cd pbrt-v2-spectral-docker
sudo docker build -t your-name/pbrt-v2-spectral-docker/ .
```

# Run a Docker Container

You can launch a Docker container from this image and use it just like a PBRT executable:
```
sudo docker run -ti ninjaben/pbrt-v2-spectral-docker pbrt --help
```

To give the container access to your PBRT scene files, mount in the current folder as a temporary volume:
```
sudo docker run -ti --rm -v `pwd`:`pwd` ninjaben/pbrt-v2-spectral-docker pbrt myScene.pbrt
```
