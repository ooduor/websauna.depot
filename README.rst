Websauna Depot
================================

This is a Python package for websauna.depot, an addon for `Websauna framework <https://websauna.org>`_.

To run this package you need Python 3.5.2+, PostgresSQL and Redis.


Installation
============

Local development mode
-----------------------

Activate the virtual environment of your Websauna application.

Then

    .. code-block:: shell

        cd websauna.depot  # This is the folder with setup.py file
        pip install -e .  # Install this package


Running the development website
===============================

Local development machine
-------------------------

Create the database:

    .. code-block:: shell

        psql create depot_dev  # Create database


.. note:: Edit the *websauna/depot/conf/development.ini* file and change the connection string to the
          one used on your environment. i.e.: postgresql://username:passwd@localhost/depot_dev


Sync models from this application to the newly created database:

    .. code-block:: shell

        ws-sync-db ws://websauna/depot/conf/development.ini


Add a user with administrative rights:

    .. code-block:: shell

        ws-create-user ws://websauna/depot/conf/development.ini admin@example.com mypassword


Start the application:

    .. code-block:: shell

        pserve ws://websauna/depot/conf/development.ini


Running the test suite
======================

First create test database:

    .. code-block:: shell

        # Create database used for unit testing
        psql create depot_test


Install test and dev dependencies (run in the folder with ``setup.py``):

    .. code-block:: shell

        pip install -e ".[dev,test]"


Run test suite using py.test running:

    .. code-block:: shell

        py.test


More information
================

Please see https://websauna.org/
