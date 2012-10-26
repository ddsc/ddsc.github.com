Server setup
============


Cassandra cluster
-----------------

Using a chef cookbook, four cassandra servers are set up, named
``d-ddsc-dfs-d1.external-nens.local`` till
``d-ddsc-dfs-d4.external-nens.local``. They run ubuntu 12.04 LTS.


Django API and lizard site
--------------------------

An ubuntu 12.04 LTS server for the `django API site
<https://github.com/ddsc/ddsc-api>`_ and for the `lizard site
<https://github.com/ddsc/ddsc-site>`_ has been set up.

The API site has already been set up in a very very initial version at
http://test.api.dijkdata.nl/ on the ``s-ddsc-ws-d1.external-nens.local``
virtual machine in Nelen&Schuurmans' Amsterdam data center. **Note**: the
domain name hasn't been coupled to the server yet, only the domain as such has
been registered.

The API site will have both a read and write API. Also included will be a
socket implementation for recieving sensor data, just like at the IJkdijk
experiment. Later on, this can be split over multiple servers if needed.

The server also has a Postgres/postgis database (later on, this has to be
moved to a separate machine).

The Lizard site hasn't been set up yet.


RabbitMQ
--------

For the time being, we use an existing Nelen&Schuurmans RabbitMQ server:
``p-flod-rmq-d1.external-nens.local``. You can see the connection data (except
the password) in the API site's `staging settings
<https://github.com/ddsc/ddsc-api/blob/master/ddsc_api/stagingsettings.py>`_.
