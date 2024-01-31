#syntax=docker/dockerfile:1.6

FROM trustworthysystems/sel4

ARG SEL4_REF=1c7a0cb549021bc0781b49aa69359ee8d035981c

# TODO(raskyld): move user mapping at runtime using a wrapper script
ARG UID=1000
ARG GID=1000

RUN groupadd -f -g $GID kernelbuilder && useradd -u $UID -g $GID --create-home kernelbuilder

USER kernelbuilder
WORKDIR /home/kernelbuilder

RUN set -eux; \
    git clone \
        https://github.com/seL4/seL4.git \
        --branch master \
        --single-branch; \
    cd seL4; \
    git checkout $SEL4_REF

ENTRYPOINT ["bash"]
