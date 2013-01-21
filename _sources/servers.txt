Server setup
============


Cassandra cluster
-----------------

Using a chef cookbook, four Cassandra servers are set up, named
``p-ddsc-cass-d1.ddsc.local`` till
``p-ddsc-cass-d4.ddsc.local``. They run Ubuntu 12.04 LTS.


Django API and lizard site
--------------------------

An Ubuntu 12.04 LTS server for the various test sites has been set up at
``s-ddsc-ws-d1.external-nens.local`` on a virtual machine in Nelen & Schuurmans'
Amsterdam data center. (See `nens-internal-only server overview page
<http://buildbot.lizardsystem.nl/serverinfo/servers/s-ddsc-ws-d1.html>`_)

Three sites are hosted there at the moment:

- The `django API site <https://github.com/ddsc/ddsc-api>`_ has already been
  set up in a very, very initial version at http://test.api.dijkdata.nl/ . The
  API site will have both a read and write API. Also included will be a socket
  implementation for receiving sensor data, just like at the IJkdijk
  experiment. Later on, this can be split over multiple servers if needed.

- The `management site <https://github.com/ddsc/ddsc-management>`_ is at
  http://test.beheer.dijkdata.nl/ .

- The `front-end Lizard site <https://github.com/ddsc/ddsc-site>`_ is at
  http://test.dijkdata.nl/ .

The Ubuntu server also has a PostgreSQL/PostGIS database locally. Later on, this
has to be moved to a separate machine.

The current structure is as follows:

.. image:: dijkdata-server-structure.png



RabbitMQ
--------

For the time being, we use an existing Nelen&Schuurmans RabbitMQ server:
``p-flod-rmq-d1.external-nens.local``. You can see the connection data (except
the password) in the API site's `staging settings
<https://github.com/ddsc/ddsc-api/blob/master/ddsc_api/stagingsettings.py>`_.


Rest API
---------

The `DDSC webclient <https://github.com/ddsc/webclient>`_ is at http://ddsc.github.com/webclient .

The communication of the webclient and the server follow this diagram:

.. image:: json-api-client-server.png
