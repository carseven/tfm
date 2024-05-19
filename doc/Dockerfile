FROM debian:bookworm
LABEL maintainer="Julian Didier (theredfish)" \
    description="A docker image based on Debian that provides pdflatex and common packages" \
    repo="https://github.com/theredfish/docker-pdflatex"

ENV DEBIAN_FRONTEND noninteractive


# Install Latex packages
COPY install.sh /install.sh
RUN sh /install.sh && rm /install.sh

WORKDIR /root/shared/folder

# Default command
ENTRYPOINT ["pdflatex"]