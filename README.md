# static-toolbox

This repository includes prebuild static binaries and build-recipes for various tools like Nmap.

The Linux versions are compiled with the [musl-cross](https://github.com/takeshixx/musl-cross) toolchain and the [openssl-pm-snapshot](https://github.com/drwetter/openssl-pm-snapshot) fork of OpenSSL in order to support a wide range of SSL/TLS features (Warning: some of them are insecure!).

## Release Packages

Precompiled and packaged releases are available in the tags/release section.

## Nmap

Precompiled versions of Nmap are available for the following operating systems/architectures:

* Linux x86 (nmap, ncat, nping)
* Linux x86_64 (nmap, ncat, nping)
* Linux armhf (nmap, ncat, nping)
* Linux aarch64 (nmap, ncat, nping)
* Windows x86 (nmap)

## Socat

Precompiled versions of socat are available for the following operating systems/architectures:

* Linux x86
* Linux x86_64

## GDB

Precompiled versions of `gdb` and `gdbserver` are available for the following operating systems/architecturs:

* Linux x86
* Linux x86_64
* Linux armhf
* Linux aarch64

# Building with Vagrant

The recipes are supposed to be built in Docker containers. In case Docker is not available, it is recommended to use Vagrant to built everything in a VM, e.g. Nmap for Linux x86:

```
vagrant up
vagrant ssh
cd /vagrant/recipes/nmap/linux_x86
sudo docker build -t static-toolbox-nmap-x86 .
sudo docker run -v $(pwd)/output:/output static-toolbox-nmap-x86
```

This is also the recommended way to run the build scripts without Docker without creating directories like `/build` and `/output` on your host system.
