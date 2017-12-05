# README

SSH server with `docker` installed in it. Can be used as a "jumper" to e.g. `docker exec` into another container.

Example:

```
docker run -d -p 2222:22 -v /var/run/docker.sock:/var/run/docker.sock -v /path/to/dir/with/authorized_keys:/root/.ssh bitrise-docker-ssh:latest
```

Simple mount a dir with an `authorized_keys` like:

```
command="docker exec -it bitrise-main-container bash" ssh-rsa AAA...t
```

Then, if you SSH into this image (in the above example, ssh into the `2222` port) you'll automatically get `docker exec`-d into
the other container (in this example the one running with a name `bitrise-main-container`).
