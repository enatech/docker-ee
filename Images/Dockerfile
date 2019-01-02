#Sample Dockerfile with explanations
#ARG is the only instruction that can preceed FROM and is used to hold arguments.
#FROM can be used multiple times in a Dockerfile. It holds the base image OS layer (can be used AS Base for next FROM statement) for a multistage build
#RUN can be used multiple times in a Dockerfile and is used to run a command
#CMD can be only once and is used to either run a command or an an entrypoint in the image execution; Same as ENTRYPOINT
#USER specify USER <UID>:<GID> so that the container will run as that user and not as root
#COPY vs ADD - both solve the same purpose except ADD can be used to copy a URL to a destination. Normally Docker recommneds using RUN to wget a URL/tar file and then unzi it as needed

ARG VERSION=1.13

FROM alpine:$VERSION as Base
RUN apk update && apk upgrade
CMD "/bin/sh" "top" "-b"

FROM alpine:latest
COPY --from=Base /file .
EXPOSE 8080
ENTRYPOINT "test" "-c"

