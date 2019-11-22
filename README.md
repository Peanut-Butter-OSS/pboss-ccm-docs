# pboss-ccm-docs
An All-Natural Customer Communications Management Solution built using pure open source building blocks and principles

## Repo strcuture
To cater for the ability to host a Spring Cloud config server in a loca git repo, while simultaneously hosting the source code in a different Git repo, we've decided to use a multi-repo strategy.

In particular:
* The Project itself will be a GitHub project (Not Repo), called PBoss-CCM
* From an IDE perspective, the pboss-ccm folder will be used as an Eclipse workspace
* A single master repo, called pboss-ccm is used to contain just this README and little else. Eventually it will serve as a meta repo
* The pboss-ccm-env repo will contain environment related files etc. This will include things like sheel scripts and docker-compose files
* The pboss-ccm-docs repo will contain the documentation and requirements
* The pboss-ccm-etc repo will contain miscellaneous things that we don't know where to store
* The pboss-ccm-testing repo will contain our test files and test code
* The pboss-ccm-config repo will contain the Spring Cloud Config git repo
* The pboss-ccm-src will contain the application source code, i.e. all microservices

## Sphinx Documentation
The project's full documentation is managed in Sphinx.

TODO - Add instructions for installing Sphinx and building the docs
