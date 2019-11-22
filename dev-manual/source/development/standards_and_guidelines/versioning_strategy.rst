.. _versioning_strategy:

Versioning Strategy
===================

The versioning strategy used for the project will be based on Semantic Versioning (https://semver.org/)

The version follows the following structure: MAJOR.MINOR.PATCH-BUILD_NUMBER

The meaning of each of these components are as follows:

MAJOR version when you make incompatible API changes,
MINOR version when you add functionality in a backwards-compatible manner, and
PATCH version when you make backwards-compatible bug fixes.
BUILD_NUMBER is an incremental number assigned by the build server.
MAJOR, MINOR and PATCH components are managed manually, i.e. they will be incremented by a project developer after each release of the project. For example

During Release 1, the version numbers will be 0.1.x-<build-number>
During Release 2, the version numbers will be 0.2.x-<build-number>
During Release 3, the version numbers will be 0.3.x-<build-number>
During Release 4, the version numbers will be 0.4.x-<build-number>
During Release 5, the version numbers will be 0.5.x-<build-number>
When going live, the version numbers will be 1.x.y-<build-number>
Note: In the pre-release stages above, the “x” will refer to the sprint number, so for example during sprint 3 of release 4, the version number will be: 0.4.2-<build-number>

Jenkins will use th Maven Version Plugin to update the version of all source code during the build process