FROM debian:buster-slim


COPY ./bcrypt /bcrypt
RUN dpkg -i /bcrypt/libxcrypt1_2.4-3ubuntu2_amd64.deb /bcrypt/libpam-unix2_2.6-2_amd64.deb
COPY /bcrypt/common-* /etc/pam.d/
COPY . /container

RUN /container/build.sh

ENV LANG="en_US.UTF-8" \
    LANGUAGE="en_US:en" \
    LC_ALL="en_US.UTF-8"

ENTRYPOINT ["/container/tool/run"]
