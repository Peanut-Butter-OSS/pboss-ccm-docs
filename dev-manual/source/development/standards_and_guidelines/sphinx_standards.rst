.. _sphinx_standards:

Sphinx Standards
================

* File Names: Lowercase, words separated by underscores, for example "installation_instructions.rst"


Sphinx Recipes
--------------

Make page width 100%
~~~~~~~~~~~~~~~~~~~~
The pages of Sphinx docs should be responsive and adapt to the screen size. 
To achieve this a custom CSS had to be added to the documentation.

The pboss-specific CSS is called pboss_theme.css and is stored in the _static folder. Content is:

.. code-block:: css

   .wy-nav-content {
       max-width: 100% !important;
    }

Then this CSS needs to be referenced from conf.py. Add the following line to conf.py:

.. code-block:: python

   def setup(app):
      app.add_stylesheet('pboss_theme.css')

