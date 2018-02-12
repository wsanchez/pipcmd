pipcmd
======

`pipcmd` is a tool for installing and managing commands installed using pip.


Installing `pipcmd`
-------------------

Installing `pipcmd` is as simple as installing the `pipcmd` script (`./bin/pipcmd`) in this source repository into a location in your `PATH`.
You will also need to set `PATH` to include the `${HOME}/.pipcmd/bin` directory, which is where `pipcmd` will install commands.


Using `pipcmd`
--------------

If the command you want to install is provided with a project with the same name as the command, simply ask `pipcmd` to install the project:

.. code-block:: console

    $ pipcmd install tox
    Installing tox from tox[latest] using python
    New python executable in /Users/wsanchez/.pipcmd/env/tox/latest/bin/python
    Installing setuptools, pip, wheel...done.
    ...
    Installing collected packages: virtualenv, pluggy, six, py, tox
    Successfully installed pluggy-0.6.0 py-1.5.2 six-1.11.0 tox-2.9.1 virtualenv-15.1.0

If a project provides a command with a different name, or mutiple commands, add the names of the commands to install:

.. code-block:: console

    $ pipcmd install twisted trial twist
    Installing trial twist from twisted[latest] using python
    New python executable in /Users/wsanchez/.pipcmd/env/twisted/latest/bin/python
    Installing setuptools, pip, wheel...done.
    ...
    Installing collected packages: incremental, hyperlink, constantly, zope.interface, attrs, six, Automat, twisted
    Successfully installed Automat-0.6.0 attrs-17.4.0 constantly-15.1.0 hyperlink-17.3.1 incremental-17.5.0 six-1.11.0 twisted-17.9.0 zope.interface-4.4.3

Note that `pipcmd` does not attempt to install every command provided by a project.
This avoids adding unwanted commands to your path, and in cases where a command name is used by multiple projects, it lets you be specific about which to install.

To list the installed commands:

.. code-block:: console

    $ pipcmd list
    tox from tox[latest] using CPython 2.7.10
    trial from twisted[latest] using CPython 2.7.10
    twist from twisted[latest] using CPython 2.7.10

To remove commands:

.. code-block:: console

    $ pipcmd remove trial tox
    Removing: trial from twisted[latest] using CPython 2.7.10
    Removing: tox from tox[latest] using CPython 2.7.10
