*****************************
Getting Started with Molecule
*****************************

Creating your first Molecule project
====================================

To create a new Ansible role with Molecule tests included from the start::

    $ molecule init role -r molecule_test

This command creates the directory structure of an Ansible role, including directories for defaults, handlers, metadata (``meta``), tasks, and variables (``vars``), plus an additional top-level directory called ``molecule`` for your tests::

   role/
   ├── defaults
   │   └── main.yml
   ├── handlers
   │   └── main.yml
   ├── meta
   │   └── main.yml
   ├── molecule
   │   └── default
   │       ├── INSTALL.rst
   │       ├── molecule.yml
   │       ├── playbook.yml
   │       └── tests
   │           └── test_default.py
   ├── README.md
   ├── tasks
   │   └── main.yml
   └── vars
       └── main.yml


Each sub-directory of the ``molecule`` directory represents a test scenario that runs on a specific virtual environment. Each test scenario includes a playbook and a configuration file as well as an ``INSTALL.rst`` file that defines the pre-requisites for the virtual environment. The default test scenario is named ``default`` and runs on Docker.

Choosing a driver
=================

To run Molecule, you need a connection to the virtual environment where it will execute tests. This connection is called a driver. The default driver for Molecule is Docker. Other options include OpenStack, Vagrant, Amazon EC2, and Microsoft Azure.

Prerequisites
-------------

Depending on the driver you choose, you may need to install additional python
packages.  If you are not already familiar with the driver you have chosen, you can create a new molecule project with the driver, then review the ``INSTALL.rst`` file from the new test scenario.
