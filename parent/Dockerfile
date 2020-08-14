FROM debian:jessie

ENV RUBY_MAJOR_MINOR 2.7
ENV RUBY_PATCH 1
ENV RUBY_VERSION 2.7.1

RUN BUILD_DIR="/tmp/ruby-build" \
 && apt-get update \
 && apt-get -y install wget build-essential zlib1g-dev libssl-dev \
    libreadline6-dev libyaml-dev tzdata \
 && mkdir -p "$BUILD_DIR" \
 && cd "$BUILD_DIR" \
 && wget -q "http://cache.ruby-lang.org/pub/ruby/2.7/ruby-2.7.1.tar.gz" \
 && tar xzf "ruby-2.7.1.tar.gz" \
 && cd "ruby-2.7.1" \
 && ./configure --enable-shared --prefix=/usr \
 && make \
 && make install \
 && cd / \
 && rm -r "$BUILD_DIR" \
 && rm -rf /var/lib/apt/lists/*

