# CED2AR3

This repository does not contain any library or application code, but instead houses documentation and
resources pertaining to CED2AR v3, and in some cases, CED2AR more generally. It also contains tools to
set up a reference implemnetation of CED2AR 3.

## Documentation

* The [wiki](https://github.com/ncrncornell/CED2AR3/wiki) associated with this repo is a good starting point.


## Architecture

CED2AR 3 has a modular architecture. While originally developed in a monorepo, it has been split up now that
development has largely stabilized for the base services in the reference implemntation. Currently, there are
actually 3 different build systems in use: primarily Maven for the rdb and core serices, but also a simple
mill script for publishing the API for different backends, and finally, SBT for the client.
