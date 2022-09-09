The base image `my-onbuild`{{}} that we just built is the result
of all of the non-ONBUILD instructions in the Dockerfile and
any container from that image will behave the same as if
the image had no ONBUILD instructions at all.

Run the Docker image we just built:
```
docker run --rm my-onbuild
```{{execute}}



- The ONBUILD instructions are embedded in the image so they can be executed at a later stage (as we'll in the next steps)
- The primary purpose of an image like this is not to be run as a container, but to be used as a base image for other downstream images.

