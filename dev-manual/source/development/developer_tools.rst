.. _developer_tools:

Developer Tools
===============

Introduction
------------
To perform optimally as a developer on this project a number of tools should be installed on your machine. 
This page documents a typical setup.

Note: Depending on your unique environment (including OS, the setup may differ)

Preferred Specifications
------------------------
* Ubuntu Linux 18.04
* 16GB RAM
* 200GB Free hard disk space

Install Git
-----------
* Note: This git install step is for Ubuntu 18.04.

.. code-block:: shell

  $ sudo apt install git

Clone repository
----------------
* After you've installing git, clone the project source code from GitHub.

TODO

Install JDK 11
--------------
TODO

Install Maven 3.5.2 (or later)
------------------------------
TODO

Install Spring Tool Suite
-------------------------
TODO


Confirgure Eclipse
------------------
* Install google styleguide. See https://github.com/HPI-Information-Systems/Metanome/wiki/Installing-the-google-styleguide-settings-in-intellij-and-eclipse
* Install eclipse style checker. See https://checkstyle.github.io/eclipse-cs/#!/
* Eclipse HTML formatting:

  #. window > preferences > web > HTML files > editor > inline elements.
  #. Select "a", "br", "img", "input", "label", "li", "select", "span", "td", "th".
  #. Click remove button and click apply button.

Install Sphinx
--------------
* Note: This git install step is for Ubuntu 18.04. For other OS see http://www.sphinx-doc.org/en/stable/install.html

.. code-block:: shell

  $ sudo pip install sphinx
  $ sudo pip install sphinx_rtd_theme
