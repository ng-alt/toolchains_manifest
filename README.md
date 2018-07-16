hndtools-arm-linux toolchain
=============================

It's yet another solution beyond the original compilation from Broadcom
to build the toolchain for its router.

The original source code of the toolchain comes from
buildroot-2012.02-source-linux-2.6.36-arm-toolchain-source.tar.bz2 within
[R6400-V1.0.0.14_1.0.8_GPL_with_toolchain_src.zip](https://www.downloads.netgear.com/files/GPL/R6400-V1.0.0.14_1.0.8_GPL_with_toolchain_src.zip). And [R6250-V1.0.0.62_with_toolchain_source.zip](https://www.downloads.netgear.com/files/GPL/R6250-V1.0.0.62_with_toolchain_source.zip) includes the binaries
`hndtools-arm-linux-2.6.36-uclibc-4.5.3.tar.bz2`.

This solution used the code from R6400-V1.0.0.14_1.0.8_GPL_with_toolchain_src.zip
and patched [buildroot](https://github.com/buildroot/buildroot) `2012.02` with
`br-external` to include the toolchain configs and patches.

It's easy to download the [git-repo](https://gerrit.googlesource.com/git-repo)
project with Google [`repo`](https://dl-ssl.google.com/dl/googlesource/git-repo/repo).

```bash
$ repo init -u git@github.com:ng-merl/toolchains_manifest -u i4u/hndtools-arm-linux/v2.6.36
$ repo sync
```

And it follows Android similar build to compile in the root of the source:

```bash
$ source build/env_setup.sh
$ lunch arm-uclibc
$ make
```
