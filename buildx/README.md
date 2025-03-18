# Multi-platform builds
A multi-platform build refers to a single build invocation that targets multiple different operating system or CPU architecture combinations. When building images, this lets you create a single image that can run on multiple platforms, such as `linux/amd64`, `linux/arm64`, and `windows/amd64`.

### Default buildx using 

```sh 
$ docker buildx use default # default buildx using 
$ docker run --privileged --rm tonistiigi/binfmt --install all
$ ls /proc/sys/fs/binfmt_misc/
$ docker run --privileged --rm tonistiigi/binfmt --install all # arch download
$ docker build --platform linux/arm64 -t test .  
```

### Docker buildx ls result 

```sh
$ docker buildx ls
NAME/NODE DRIVER/ENDPOINT STATUS  BUILDKIT PLATFORMS
default * docker
  default default         running v0.12.5  linux/amd64, linux/amd64/v2, linux/amd64/v3, linux/amd64/v4, linux/386, linux/arm64, linux/riscv64, linux/ppc64le, linux/s390x, linux/mips64le, linux/mips64, linux/arm/v7, linux/arm/v6
```