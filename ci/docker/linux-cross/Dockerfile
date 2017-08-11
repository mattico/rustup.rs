FROM alexcrichton/rust-slave-linux-cross:2017-02-02

USER root

# Only required locally
RUN curl https://sh.rustup.rs -sSf | sh -s -- --default-toolchain nightly -y

RUN for f in `ls /x-tools/*-unknown-linux-*/bin/*-unknown-linux-*`; do          \
        g=`basename $f`;                                                        \
        ln -vs $f /usr/bin/$g;                                                  \
    done

USER rustbuild