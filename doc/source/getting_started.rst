*****************************
Getting Started with Molecule
*****************************

Creating your first project
===========================

To create an Ansible role with Molecule tests built in from the start, create a Molecule project::

    $ molecule init role -r molecule_test

This command creates the directory structure of an Ansible role, including directories for defaults, handlers, metadata (``meta``), tasks, and variables (``vars``), plus an additional directory called ``molecule``. Each sub-directory of the ``molecule`` directory represents a test scenario that runs on a specific virtual environment. Each test scenario includes a playbook and a configuration file as well as an ``INSTALL.rst`` file that defines the pre-requisites for the virtual environment. The example above creates a single test scenario called ``default``, which will run on Docker.

Choosing a driver
=================

To run Molecule, you need a connection to the virtual environment where it will execute tests. This connection is called a driver. The default driver for Molecule is Docker. Other options include OpenStack, Vagrant, Amazon EC2, and Microsoft Azure.

Requirements
------------

Depending on the driver you choose, you may need to install additional python
packages.  See the driver's documentation or `INSTALL.rst`, which is created
when initializing a new scenario.
