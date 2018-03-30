** Cross Compiler for Raspberry Pi on a Docker container

'''
$ docker pull ragnaroek/rust-raspberry:1.25.0
$ docker run \
    --volume <path to your rust project directory>:/home/cross/project \
    --volume <path to directory containing the platform dependencies>:/home/cross/deb-deps \ # optional, see section "Platform dependencies"
    --volume <path to local cargo registry, e.g. ~/.cargo/registry>:/home/cross/.cargo/registry \ # optional, using cached registry avoids updating on every build
    ragnaroek/rust-raspberry:<version>
    <cargo command> # e.g. "build --release"
'''
