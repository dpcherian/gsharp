Introduction
============



Basic Instructions
==================

.. caution:: This machine is for cpu-intensive jobs. Common jobs like editing, word-processing, graph or figure drawing, etc. should be avoided as far as possible.


Installation
~~~~~~~~~~~~

You need to login to the server using SSH, also referred to as `Secure Shell`. The SSH protocol is a method to login securely from your computer (the "client" system) to a remote machine (the "server") and transfer files between them.

MacOS
-----

All modern Macs running macOS or Mac OS X come with SSH pre-installed by default. 


Linux
-----

Most Linux systems come with an SSH client preinstalled. A popular client is `OpenSSH <https://en.wikipedia.org/wiki/OpenSSH>`_. To check whether OpenSSH is installed, run the following command in a terminal window which should give you the version of OpenSSH installed:

.. code-block:: bash

  ssh -V

If you get an error informing you that the ``ssh`` command is not installed, you need to install OpenSSH. On Debian-based distributions like Ubuntu and Linux Mint this can be done using

.. code-block:: bash

  sudo apt install openssh-client

Windows
-------

On Windows, the simplest way to get SSH is to install `Putty <https://www.putty.org/>`_. Once Putty has been installed, you can Putty's GUI to connect to the server as described in :ref:`Logging in with Putty <login-with-putty>`, or through Window's PowerShell using the ``ssh`` command, as in Linux or MacOS.

Logging in
~~~~~~~~~~

Logging in using the terminal
-----------------------------


.. _login-with-putty:

Logging in with Putty
---------------------



Setting up passwordless login
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

For security, a password-less connection should be used.


