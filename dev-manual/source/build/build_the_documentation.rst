.. raw:: latex

    \newpage

Build the Documentation
=======================

The documentation for this project is done using Sphinx. It can be generated to HTML or PDF. the steps for each is documented below

HTML
----
* cd into the Documentation folder. For example: Repos/PBOSS/pboss_ccm/pboss_ccm_docs/dev-manual
* run this command: "make html"
* Once complete, the documentation can be found in the build/html subfolder

Note 1: If the builder gives any errors, read them carefully, understand them and fix the source code. Then regenerate
Note 2: Form time to time it makes sense to do a clean build. In such cases, first rebuild the entire "build" folder, for example Repos/Sarb/AEM_Implementation/Documentation/build

PDF
---
* cd into the Documentation folder. For example: Repos/PBOSS/pboss_ccm/pboss_ccm_docs/dev-manual
* run this command: "make latexpdf"
* Once complete, the documentation can be found in the build/latex subfolder

Note: The PDF generation capability requires LaTeX to be installed on the machine that generates the docs.
