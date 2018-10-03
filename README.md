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
mill script for publishing the API for different backends, and finally, SBT for the client. In principle, 
it would likely be possible to switch most of these to `mill`, though for now we've used the most appropriate
build tool for each case. There are benefits to using `mill` for every project, since `mill` can be used to do
a true [multi-project build](https://github.com/jackkoenig/mill-multi-project) using imports.

Additionally, we use primary two languages: Scala and Java. Some modules are either one 
or the other, except core-services, which currently uses both languages.


`ced2ar3-api` provides datatypes that can be used both on the client (compiled to JavaScript) and on the server.
The client packages that make use of `ced2ar3-api` include services and potentially the `ced2ar3-site` modules,
while the client is just `ced2ar3-client`.
