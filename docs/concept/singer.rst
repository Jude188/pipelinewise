
.. _singer:

Singer.io
---------

PipelineWise is using the `Singer.io <https://www.singer.io/>`_
specification to replicate data from various sources to various destinations.

Singer is an `Open Source Standard <https://github.com/singer-io/getting-started/blob/master/docs/SPEC.md>`_
for moving data between databases, web APIs, files, queues, and just about anything else
you can think of. The Singer spec describes how data extraction scripts — called :ref:`taps`
— and data loading scripts — called :ref:`Targets` — should communicate using a standard
JSON-based data format over stdout. By conforming to this spec, Taps and Targets can be
used in any combination to move data from any source to any destination.

Original article and further details at https://github.com/singer-io/getting-started


Core Concepts
'''''''''''''

.. _taps:

Taps
====

Taps are designed to produce a stream of data from sources like databases and web service APIs
for use in a data integration or ETL pipeline.

A Tap is an application that takes a configuration file and an optional state file as input
and produces an ordered stream of record, state and schema messages as output.
A **record** is json-encoded data of any kind. A **state message** is used to persist information
between invocations of a Tap. A **schema message** describes the datatypes of the records in the stream.

Using PipelineWise you don't need to know these singer messages in details, however if you're
interested you can find more details in the official `Singer Specification <https://github.com/singer-io/getting-started/blob/master/docs/SPEC.md>`_.
A number of of taps developed by Singer.io or by other members of the community are open
sourced and can be added to PipelineWise relatively easily.

List of the currently supported and built-in taps in PipelineWise is in the :ref:`taps_list` section.


.. _targets:

Targets
=======

Targets are designed to consume streams that generated by a Tap like loading data into a Postgres
or Snowflake database.

Following the singer specification every Target can consume messages from every Tap, making it
possible to replicate data from various sources to various destinations.


List of the supported targets and built-in taps in PipelineWise can be found in the :ref:`targets_list` section.
