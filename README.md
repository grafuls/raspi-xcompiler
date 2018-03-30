** Cross Compiler for Raspberry Pi on a Docker container

'''
$ git clone https://github.com/grafuls/rust-on-raspberry-docker.git
$ cd rust-on-raspberry-docker
$ docker build -t rust-xcompiler:latest . --no-cache

$ docker run \
    --volume <path to your rust project directory>:/home/cross/project \
    --volume <path to directory containing the platform dependencies>:/home/cross/deb-deps \ # optional, see section "Platform dependencies"
    --volume <path to local cargo registry, e.g. ~/.cargo/registry>:/home/cross/.cargo/registry \ # optional, using cached registry avoids updating on every build
    rust-xcompiler
    <cargo command> # e.g. "build --release"
'''
