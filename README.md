# pboss-ccm-docs
An All-Natural Customer Communications Management Solution built using pure open source building blocks and principles

## Repo structure
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

## Your first PBoss sarmie
If this is your first interaction with PBOSS CCM, we'd suggest taking the following steps:

Step 1: Create a root folder on your file system, we will call this PROJECT_ROOT in the instructions below

Step 2: Clone each of the repos (listed above) directly underneath PROJECT_ROOT, creating a structure like this:

''' PROJECT_ROOT
'''   |
'''   +--pboss-ccm-env
'''   +--pboss-ccm-docs
'''   +--pboss-ccm-etc
'''   +--pboss-ccm-testing
'''   +--pboss-ccm-config
'''   +--pboss-ccm-src
'''         |
'''         +--pboss-ccm-config-server
'''         +--pboss-ccm-core-engine
'''         +--pboss-ccm-core-utils
'''         +--pboss-ccm-eureka
'''         +--pboss-ccm-model
'''         +--pboss-ccm-on-demand-api
'''         +--pboss-ccm-on-demand-request-svc
'''         +--pboss-ccm-test-edge-svc
'''         +--pboss-ccm-test-svc

Step 3: Build and run the Config SpringBoot app

Step 4: Build and run the Eureka SpringBoot app

Step 5: Build and run the on-demand-api SpringBoot app

Step 6: Build and run the on-demand-request-svc SpringBoot app

Step 7: Import the Postman collection

* Make sure you have PostMan installed on your local machine
* Import the Postman collection (/pboss-ccm/pboss-ccm-testing/Postman/PBoss_CCM.postman_collection.json) into your postman

Step 8: Send a test request


## Sphinx Documentation
The project's full documentation is managed in Sphinx.

TODO - Add instructions for installing Sphinx and building the docs


