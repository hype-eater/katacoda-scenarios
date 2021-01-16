Create the Dockerfile for a "downstream" image, one that uses the base we just built.
<pre class="file" data-filename="downstream/Dockerfile" data-target="replace">
FROM my-onbuild
RUN echo "three" >> things.txt
</pre>


Build the image.
`docker build —t my-downstream downstream`{{execute}}


Run a container
`docker run --rm my-downstream`{{execute}}