Start with a basic Dockerfile.

<pre class="file" data-filename="base/Dockerfile" data-target="replace">
FROM alpine

RUN echo "regular run"
RUN echo "one" >> things.txt

ENTRYPOINT ["cat", "things.txt"]
</pre>

Add some ONBUILD instructions.
<pre class="file" data-filename="base/Dockerfile" data-target="append">
ONBUILD ARG CUSTOM_WORD=two
ONBUILD RUN echo "onbuild run"
ONBUILD RUN echo "$CUSTOM_WORD" >> things.txt
</pre>

Build the Docker image:
```docker build -t my-onbuild base```{{execute}}

