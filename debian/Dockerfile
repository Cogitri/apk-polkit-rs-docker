FROM rust:1-slim-buster
RUN apt-get update \
	&& DEBIAN_FRONTEND=noninteractive apt-get -y install git build-essential \
		dbus-x11 python3-dbusmock gettext lua5.3 lua-zlib appstream-util \
		appstream rustc cargo python3-pip libssl-dev pkg-config llvm \
		libglib2.0-dev-bin libglib2.0-dev policykit-1 lcov libc6-dbg \
	&& pip3 install meson ninja \
	&& rustup update nightly && rustup default nightly && cargo install grcov \
    && git clone https://gitlab.alpinelinux.org/alpine/abuild \
    && cd abuild && sed 's|bin/ash|bin/bash|g' -i *.in && make install \
	&& cd .. rm -rf abuild
