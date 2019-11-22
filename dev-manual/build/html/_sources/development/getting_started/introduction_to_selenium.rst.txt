Introduction to Selenium
========================

TODO

WebDrivers
----------
To run automated Selenium tests you will use WebDrivers - These allow our test code to launch a new web browser
and execute tests on it.

You will need to install the following WebDrivers:

* On Linux
    * FireFox (Gecko)
    * Chrome
    * PhantomJS
* On Windows
    * FireFox (Gecko)
    * Chrome
    * PhantomJS 
    * Internet Explorer 
    * Edge

Install ChromeDriver
^^^^^^^^^^^^^^^^^^^^

To install ChromeDriver you need to:

* Have Chrome installed on your machine
* Then Install the latest version of ChromeDriver

To install Chrome on RHEL:

.. code-block:: bash

    $ wget https://dl.google.com/linux/direct/google-chrome-stable_current_x86_64.rpm
    $ sudo yum install ./google-chrome-stable_current_*.rpm

To install ChromeDriver:

(link below assumes 2.37 is the latest version, but first double check)

.. code-block:: bash

    $ wget https://chromedriver.storage.googleapis.com/2.37/chromedriver_linux64.zip

On the DevOps server, the ChromeDriver is stored at

/opt/SeleniumWebDrivers/chromedriver


PhantomJS
---------
PhantomJS is a headless WebKit with JavaScript API. It can be used for headless website testing.

To install PhantomJS on your Ubuntu machine, please run:

.. code-block:: bash

    $ sudo apt-get install phantomjs
    
Note: We're still deciding whether it makes sense to run PhantomJS or whether we should simply run Chrome in headless mode

Reference Links
---------------
* https://www.seleniumhq.org/
* http://www.automationtestinghub.com/selenium-3-0-launch-firefox-with-geckodriver/
* http://www.automationtestinghub.com/selenium-chromedriver/
* http://www.automationtestinghub.com/selenium-3-launch-microsoft-edge-with-microsoftwebdriver/
* https://christopher.su/2015/selenium-chromedriver-ubuntu/
* https://sites.google.com/a/chromium.org/chromedriver/downloads
* https://scotch.io/tutorials/what-is-phantomjs-and-how-is-it-used