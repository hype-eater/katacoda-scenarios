Start with a basic Dockerfile.

```
FROM alpine

RUN echo "regular run"
RUN echo "one" >> things.txt

ENTRYPOINT ["cat", "things.txt"]
```{{}}

Add some ONBUILD instructions.
```
ONBUILD ARG CUSTOM_WORD=two
ONBUILD RUN echo "onbuild run"
ONBUILD RUN echo "$CUSTOM_WORD" >> things.txt
```{{ copy }}

Build the Docker image:
```
docker build -t my-onbuild /base
```{{ exec }}

