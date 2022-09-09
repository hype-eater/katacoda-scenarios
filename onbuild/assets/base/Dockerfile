FROM alpine

RUN echo "regular run"
RUN echo "one" >> things.txt

ENTRYPOINT ["cat", "things.txt"]

ONBUILD ARG CUSTOM_WORD=two
ONBUILD RUN echo "onbuild run"
ONBUILD RUN echo "$CUSTOM_WORD" >> things.txt
