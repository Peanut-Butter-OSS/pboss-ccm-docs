.. _maven_standards:

Maven Standards
===============

Maven standards for the project are aligned to https://maven.apache.org/guides/mini/guide-naming-conventions.html

Group Id
--------
The Group Id for the parent project will be: org.pboss.ccm

Artifact Id
-----------
Artifact Id is the name of the jar without version.

Lowercase with words separated by dashes, for example: data-staging-service

Version
-------
Versioning should align with the project versioning strategy, as defined at: :ref:`Versioning Strategy <versioning_strategy>`

The project uses the Maven version plugin to manage versions (see: https://www.mojohaus.org/versions-maven-plugin/)

To update the project version, run this command at the root of the REPO:

.. code-block:: bash

   mvn versions:set -DnewVersion=x.y.z-<descriptor>

The above command will update the version of the parent POM and all downstream references to it.

In the source repo, the descriptor should generally always be SNAPSHOT, for builds done by Jenkins, the Jenkins build number will be used as the descriptor. 

First review the changes made by the plugin using git status (for example).

If you are happy with the changes, run:

.. code-block:: bash

   mvn versions:commit

If you are unhappy and would like to revert, please run:

.. code-block:: bash

   mvn versions:revert

Note: Read here for an overview of how the Maven Version plugin should be used: https://www.mojohaus.org/versions-maven-plugin/usage.html

Maven Properties
----------------
All Maven versions must be defined as properties in the parent POM. This ensures that the entire project uses the same 
versions throughout.

Current standard followed is version.package-being-versioned, for example version.slf4j

There are some interesting other opinions (for example, https://stackoverflow.com/questions/30297777/convention-for-maven-properties-dot-case-or-camel-case), but we'll keep going as we've started.

Maven Plugin Management
-----------------------
The root POM defines a pluginManagement section which defines all plugins that are available for the whole project.

Sub-modules should simply refer to these plugins.

Maven Reporting
---------------
Maven site reporting is used to generate various reports for the application. 

The report should be generated from the root of the project using the following command:

.. code-block:: bash

   mvn clean site
   
Once this is done, you can run the following command to stage the stire for viewing:

.. code-block:: bash

   mvn site:stage
   
Once it is stages, the whole site is ready to be picked up at [REPO_HOME]/target/staging
   
Maven Build
-----------
The whole application can be built from the root folder using the following command:

.. code-block:: bash

   mvn clean install -PautoInstallPackage,adobe-public














