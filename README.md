# pboss-ccm-docs
An All-Natural Customer Communications Management Solution built using pure open source building blocks and principles

## Repo structure
To cater for the ability to host a Spring Cloud config server in a loca git repo, while simultaneously hosting the source code in a different Git repo, we've decided to use a multi-repo strategy.

In particular:
* The Project itself will be a GitHub project (Not Repo), called PBoss-CCM
* From an IDE perspective, the pboss-ccm folder will be used as an Eclipse workspace
* A single master repo, called pboss-ccm is used to contain just this README and little else. Eventually it will serve as a meta repo
* The pboss-ccm-env repo will contain environment related files etc. This will include things like shell scripts and docker-compose files
* The pboss-ccm-docs repo will contain the documentation and requirements
* The pboss-ccm-etc repo will contain miscellaneous things that we don't know where to store
* The pboss-ccm-testing repo will contain our test files and test code
* The pboss-ccm-config-repo repo will contain the Spring Cloud Config git repo. This is where the configs of all services are maintained
* The pboss-ccm-src will contain the application source code, i.e. all microservices

## Your first peanut butter sarmie
If this is your first interaction with PBOSS CCM, we'd suggest taking the following steps:

Note: These steps will obviously be simplified once the SpringBoot conversion is complete

Step 1: Create a root folder on your file system, we will call this PROJECT_ROOT in the instructions below

Step 2: Clone each of the repos (listed above) directly underneath PROJECT_ROOT, creating a structure like this:

    PROJECT_ROOT
    ├── pboss-ccm-config-repo
    ├── pboss-ccm-docs
    ├── pboss-ccm-env
    ├── pboss-ccm-etc
    ├── pboss-ccm-src
    │   ├── pboss-ccm-config-server
    │   ├── pboss-ccm-core-engine
    │   ├── pboss-ccm-core-utils
    │   ├── pboss-ccm-eureka
    │   ├── pboss-ccm-model
    │   ├── pboss-ccm-on-demand-api
    │   ├── pboss-ccm-on-demand-request-svc
    │   ├── pboss-ccm-test-edge-svc
    │   ├── pboss-ccm-test-svc
    ├── pboss-ccm-testing
    └── Servers

Step 3: Start Rabbit MQ docker container

    cd [PROJECT_ROOT]/pboss-ccm-env/docker
    docker-compose up
    
    Confirm the server is up by accessing http://localhost:9072/
    Note: default credentials are guest:guest

Step 4: Build and run the Config Server SpringBoot app

    cd [PROJECT_ROOT]/pboss-ccm-src/pboss-ccm-config-server
    mvn clean install
    java -jar target/pboss-ccm-config-server-0.0.1-SNAPSHOT.jar 
    or
    mvn spring-boot:run
    
    Confirm server is up by accessing: http://localhost:8888/actuator/health

Step 5: Build and run the Eureka SpringBoot app

    cd [PROJECT_ROOT]/pboss-ccm-src/pboss-ccm-eureka
    mvn clean install
    java -jar target/pboss-ccm-eureka-0.0.1-SNAPSHOT.jar 
    or
    mvn spring-boot:run
    
    Confirm server is running by accessing: http://localhost:8761/ 

Step 6: Build the model project

    cd [PROJECT_ROOT]/pboss-ccm-src/pboss-ccm-model
    mvn clean install

Step 7: Build the utils project

    cd [PROJECT_ROOT]/pboss-ccm-src/pboss-ccm-utils
    mvn clean install

Step 8: Import the Postman collection

* Make sure you have PostMan installed on your local machine
* Import the Postman collection (/pboss-ccm/pboss-ccm-testing/Postman/PBoss_CCM.postman_collection.json) into your postman

Step 9: Build and run the pboss-ccm-on-demand-request-svc SpringBoot app

    cd [PROJECT_ROOT]/pboss-ccm-src/pboss-ccm-on-demand-request-svc
    mvn clean install
    java -jar target/pboss-ccm-on-demand-request-svc-0.0.1-SNAPSHOT.jar
    or
    mvn spring-boot:run
    
    To confirm the service is running, submit the following request from PostMan: OnDemandRequestSvc_INTERNAL/Submit_SanityTest
	Note: you can also open the RabbitMQ console and check that a message appears in the pboss.ccm.master queue

Step 10: Build and run the on-demand-api SpringBoot app

    cd [PROJECT_ROOT]/pboss-ccm-src/pboss-ccm-on-demand-api
    mvn clean install
    java -jar target/pboss-ccm-on-demand-api-0.0.1-SNAPSHOT.jar
    or
    mvn spring-boot:run

    To confirm the service is running, submit the following request from PostMan: OnDemandApi_EDGE/EDGE_Submit_SanityTest
	Note: you can also open the RabbitMQ console and check that a message appears in the pboss.ccm.master queue

Step 11: Build and run the core-engine SpringBoot app

    cd [PROJECT_ROOT]/pboss-ccm-src/pboss-ccm-core-engine
    mvn clean install
    java -jar target/pboss-ccm-core-engine-0.0.1-SNAPSHOT.jar
    or
    mvn spring-boot:run
    
Step 12: End-to-end Test - Not final yet

* At this point you should be able to submit a request to the On-Demand-Api and it will be processed by the core processor
* Submit the following request from PostMan: OnDemandApi_EDGE/EDGE_Submit_SanityTest
* Monitor the core processor log to confirm it was picked up successfully

Step n: No be added later

* TODO


## Sphinx Documentation
The project's full documentation is managed in Sphinx.

TODO - Add instructions for installing Sphinx and building the docs


