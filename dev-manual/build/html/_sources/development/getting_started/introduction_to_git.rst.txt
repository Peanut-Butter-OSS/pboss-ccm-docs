Introduction to Git
===================

Cheatsheet - Branching
----------------------
List local branches:

.. code-block:: shell

    $ git branch

List remote branches:

.. code-block:: shell

    $ git branch -r

Delete local branch:

.. code-block:: shell

    $ git branch -d <your-branch>

Delete remote branch:

.. code-block:: shell

    $ git push origin --delete <your-branch>

Checkout a remote branch (creating a tracking local branch):

.. code-block:: shell

    $ git branch <localbranch> <remote>/<remotebranch>

Remove stale references to old remote branches:

.. code-block:: shell

    $ git remote prune <remote>

Remove a file from the repo that was added accidentally (Removes it from source control)

.. code-block:: shell

    $ git rm --cached <path/filename>

Remove a folder from the repo that was added accidentally (Removes it from source control)

.. code-block:: shell

    $ git rm -r --cached <path/to/folder>

View all remotes in verbose module

.. code-block:: shell

    $ git remote -v

Reference Links
---------------
