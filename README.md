Fuzzilli For quickjs
====================
A set of patches to run
[Fuzzilli](https://github.com/googleprojectzero/fuzzilli) for quickjs.

```bash

# Build quickjs for Fuzzilli
$ wget https://bellard.org/quickjs/quickjs-2019-09-01.tar.xz
$ tar -xvf quickjs-2019-09-01.tar.xz
$ cd quickjs-2019-09-01
$ patch -p0 < ../quickjs.patch
$ make -j$(nproc)

# Build Fuzzilli
$ git clone https://github.com/googleprojectzero/fuzzilli
$ cd fuzzilli
$ patch -p0 < ../fuzzilli.patch
$ swift build

# Run Fuzzilli for quickjs
$ swift run FuzzilliCli --profile=quickjs --storagePath=./output ../quickjs-2019-09-01/qjs
```

Happy hacking :)
