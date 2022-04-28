
FROM        --platform=$TARGETOS/$TARGETARCH node:17-alpine

LABEL       author="Vitaly Ruhl" maintainer="pterodactyl@vitaly-ruhlde"

LABEL       org.opencontainers.image.source="https://github.com/vitalyruhl/thomas-docker-image"
LABEL       org.opencontainers.image.licenses=MIT

RUN         apk add --update --no-cache ca-certificates curl ffmpeg git openssl sqlite tar tzdata chromium \
	&& adduser -D -h /home/container container

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/ash", "/entrypoint.sh" ]
