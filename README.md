# pbrt-v2-spectral-docker
Dockerfile and instructions for building [pbrt-v2-spectral](https://github.com/ydnality/pbrt-v2-spectral), a customized version of the PBRT renderer.

# Hi!

The `Dockerfile` in this repository represents a complete set of instructions for building pbrt-v2-spectral on Ubuntu.  You can use this to create a Docker image with PBRT in it.

You can also consult this to figure out how to build PBRT.  The RUN commands are thing you can run on the command line.  Some of them will require `sudo`.

# Build the Docker image

Here's how to build the image in the first place:
 - [install Docker](https://docs.docker.com/installation/)
   - on ubuntu (might be out-dated): `sudo apt-get install docker docker.io`
   - on amazon linux: `sudo yum install docker`
 - `sudo service docker start`
 - [install Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
   - on ubuntu: `sudo apt-get install git`
   - on amazon linux: `sudo yum install git`
 - `git clone https://github.com/benjamin-heasly/pbrt-vs-spectral-docker.git`
 - `cd pbrt-vs-spectral-docker`
 - `sudo docker build -t my-name/pbrt-vs-spectral-docker:latest .`

# Run the Docker image

Here's how to launch a Docker container from the image, and get command line access:
 - `sudo docker run -t -i my-name/pbrt-vs-spectral-docker:latest "/bin/bash"`

Once you're in, check that you can run pbrt:
 - `./pbrt`

# Automated Docker Hub builds?

Since the `Dockerfile` is nearly self-contained, it would make a nice automated build on Docker Hub.  That way, you wouldn't have to build the image yourself.  I haven't set this up but it should be possible, assuming Docker Hub provides sufficient resources for doing the build.

Alternatively, if you have a Docker Hub account, you can push up the image manually, then use it from anywhere.  That way, you only have to build the image once:
 - `sudo docker login`
 - `sudo docker push my-name/pbrt-vs-spectral-docker:latest`
