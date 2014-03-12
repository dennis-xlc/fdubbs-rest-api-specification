This repository contains the documentation and JSON schema specification for [Fudan BBS](http://bbs.fudan.edu.cn/).

Documentation
=============

Please see the domain model and human description of the specification [here](v1/README.md).

The release note of the initial v1 implementation can be found [here](v1/doc/RELEASENOTES.md).

The user guide for clients of services implementing this spec can be found [here](v1/doc/USERGUIDE.md).

Schema
=======
The [JSON Schema](http://json-schema.org) can be found [here](v1/schema). The [Google Discovery Document](https://developers.google.com/discovery/v1/reference/apis) for the service is [here](v1/schema/api.json).

The maven artifact for this specification can be found [here](v1/pom.xml).

Which Branch to use?
--------------------
Please use the `develop` branch to make changes as required during the specification/development phase. 

Once the spec is final, create a new branch `release-x.x` from the `develop` branch. When the `release-x.x` goes live, merge the changes with the `master`.

The `master` always contains the last released API specification that's in live.
