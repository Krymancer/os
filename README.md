# 64-bit Operating System Kernel

## Prerequisites

- [Docker](https://www.docker.com/) for creating our build-environment.
- [Qemu](https://www.qemu.org/) for emulating our operating system.

## Setup

Build an image for our build-environment:

- `docker build buildenv -t os-buildenv`

## Build

Enter build environment:

- `sudo docker run --rm -it -v "$PWD":/root/env os-buildenv`

Build for x86 (other architectures may come in the future):

- `make build-x86_64`

To leave the build environment, enter `exit`.

## Emulate

You can emulate your operating system using [Qemu](https://www.qemu.org/): (Don't forget to add qemu to your path!)

- `qemu-system-x86_64 -cdrom dist/x86_64/kernel.iso`

## Cleanup

Remove the build-evironment image:

- `docker rmi os-buildenv -f`
