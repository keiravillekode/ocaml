FROM ocaml/opam:debian-11-ocaml-5.1-afl

USER root

RUN apt-get update \
    && apt-get install -y m4 bmake cpio net-tools fswatch pkg-config \
    && rm -rf /var/lib/apt/lists/*

RUN git config --global --add safe.directory "*"

RUN cd /home/opam/opam-repository \
    && git pull origin master

RUN opam update \
    && opam install core \
    core_unix \
    yaml \
    ezjsonm \
    mustache \
    dune \
    fpath \
    ocamlfind \
    ounit \
    ounit2 \
    qcheck \
    react \
    ppx_deriving \
    ppx_let \
    ppx_sexp_conv \
    yojson \
    ocp-indent \
    calendar \
    getopt \
    stdio

ENV PATH="/home/opam/.opam/5.1/bin:${PATH}" \
    MAKESYSPATH=/usr/share/bmake/mk-bmake