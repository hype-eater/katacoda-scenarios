Now, build another "downstream" image that uses the same base we built earlier.
By specifying build args, we'll impact the behavior of the ONBUILD instructions.
Even though the ONBUILD instructions are embedded in the previously-built base image,
they don't run until the downstream build, so the context of the downstream build affects
the outcomes of the ONBUILD instructions.


Build the image.
```
docker build --build-arg CUSTOM_WORD=bananas -t my-other-downstream /downstream
```{{execute}}


Run a container
```
docker run --rm my-other-downstream
```{{execute}}