Remote Embedded DIANA Setup
===========================

Derek Merck  
<derek_merck@brown.edu>  
Rhode Island Hospital and Brown University  
Providence, RI  

Setup a multi-arch [Diana](https://github.com/derekmerck/diana) DICOM-handler service on embedded systems.


Use It
----------------------

```bash
$ docker-compose up
```

When using Resin.io devices in "local mode" for development and testing, you can also [direct the device's Docker daemon remotely][dev-test].

```bash
$ DOCKER_API_VERSION=1.22 DOCKER_HOST=tcp://device_name.local:2375 docker-compose up -d
```

[dev-test]: https://github.com/resin-io-playground/resinos-compose


Docker Image Dependencies
-------------------------

- [redis](https://hub.docker.com/_/redis/)
- [derekmerck/orthanc](https://github.com/derekmerck/orthanc-xarch)
- [derekmerck/conda](https://github.com/derekmerck/conda-xarch)
- [derekmerck/keras-tf](https://github.com/derekmerck/conda-xarch)

Depending on configuration.


Supported Architectures
-----------------------

Tested on an Intel-based machine and Raspberry Pi.  Can be compiled for `aarch64`, but not tested.

Dependencies are are all multi-architecture, so the image name alone is typically sufficient to find the correct image when pushing to a range of devices.  When uploading via [Resin.io][], you may need to add explicit "arm32v7" tags for the Raspberry Pi because their builder is `aarch64` and will look for an "arm64v8" tag by preference rather than the base image target arch.

[Resin.io]: http://resin.io


License
-------

MIT
