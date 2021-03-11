FROM ruby:2.7

WORKDIR /root

ADD install-pdk-release.sh .
ADD pdk-release.env .

RUN apt-get update && \
    apt-get install -y curl openssh-client && \
    ./install-pdk-release.sh

ENV PATH="${PATH}:/opt/puppetlabs/pdk/private/git/bin"
ENV PDK_DISABLE_ANALYTICS=true

ENTRYPOINT ["/opt/puppetlabs/pdk/bin/pdk"]
