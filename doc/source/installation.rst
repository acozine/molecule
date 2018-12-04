.. _installation:

***********************************************
Installing Molecule and a Virtualization Driver
***********************************************

Molecule is a Python package that's distributed via PyPI. You can install it via ``pip`` or from the source repository. If you want the stable version of Molecule, install with ``pip``. If you want to contribute to the Molecule project, and/or use cutting-edge features, install from source.

To run Molecule, you also need to install a connection to a virtualization platform, called a driver. The default driver is Docker, but Molecule can also run on Vagrant and on most of the major cloud providers.

Installing Molecule with ``pip``
================================

The quickest way to install Molecule is with the Python package manager, ``pip``.

Prerequisites
-------------

Before you can install Molecule with ``pip``, you must have Python installed. Depending on the system you are running, you may need additional packages.

* :std:doc:`Ansible <ansible:index>` >= 2.4
* Python 2.7
* Python >= 3.6 with Ansible >= 2.4

CentOS 7
^^^^^^^^

.. code-block:: bash

    $ sudo yum install -y epel-release
    $ sudo yum install -y gcc python-pip python-devel openssl-devel libselinux-python

Ubuntu 16.x
^^^^^^^^^^^

.. code-block:: bash

    $ sudo apt-get update
    $ sudo apt-get install -y python-pip libssl-dev

Install with ``pip``
--------------------

``pip install molecule``

:std:doc:`pip <pip:usage>` is the only supported installation method.

On some versions of macOS, you may see an error message ``could not create '/System/Library/Frameworks/Python.framework/Versions/2.7/share': Operation not permitted`` when you do ``pip install molecule``. If you run into this, install Molecule at the user level instead of system-wide:

``pip install molecule --user``

Then make sure ``~/Library/Python/2.7/bin/`` is on your $PATH.

Install
-------

Install Molecule:

.. code-block:: bash

    $ pip install --user molecule

Installing molecule package also installed its main script ``molecule``,
usually in ``PATH``. Users should know that molecule can also be called as a
python module, using ``python -m molecule ...``. This alternative method has
some benefits:

* allows to explicitly control which python interpreter is used by molecule
* allows molecule installation at user level without even needing to have
  the script in ``PATH``.

Installing Molecule from source
===============================

Due to the rapid pace of development on this tool, you might want to install it
in "`development mode`_" so that new updates can be obtained by simply doing a
``git pull`` in the repository's directory.

Prerequisites
-------------

CentOS 7
^^^^^^^^

.. code-block:: bash

    $ sudo yum install -y libffi-devel git

Ubuntu 16.x
^^^^^^^^^^^

.. code-block:: bash

    $ sudo apt-get install -y libffi-dev git

Install from source
-------------------

.. code-block:: bash

    $ git clone
    $ cd /path/to/molecule/checkout
    $ pip install -U -e .

.. _`development mode`: https://setuptools.readthedocs.io/en/latest/setuptools.html#development-mode
