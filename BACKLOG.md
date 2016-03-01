General
=======

SS ACL export/import
--------------------

Security server must support exporting and importing of access rights of
the services.

Shell scripts for executing meta-services
-----------------------------------------------

Create a simple command line scripts to execute management services.

Cost effective trust service consumption
----------------------------------------

Prefetching of OCSP must be configurable. When cost effective option is
selected then OCSP fetching should be executed only when needed.

Signature format documentation sufficiently described with examples to build external validators.
-------------------------------------------------------------------------------------------------

Create a better documentation of signature format used by X-Road and
provide that with examples. Documentation must be sufficient to build
external validators.

SS Hi-Availability
------------------

Create a new Hi-availability solution for clustering security servers
(needs researching first).

RIA JIRA
========

CSR format of trust service provider
------------------------------------

It must be possible to save in X-Road center the preference for CSR
(certificate signing request) format for every trust service provider.
Generation of CSR in security server must automatically select the
correct format (XTE-187).

Management services monitoring
----------------------------------

It must be possible to monitor whether management services are working
(XTE-183). The main purpose is to monitor whether central server is
fulfilling its SLA (service level agreement) without overwhelming the
logs with test requests.

Subsystem full name
-------------------

Make it possible to add full name to subsystem. Full name should be
visible not only in the web interface of security and central servers,
but also in metaservices (XTE-149).

Metaservice listClients extra field isProducer
----------------------------------------------

Metaservice listClients should output an extra field isProducer that
indicates whether member or subsystem is offering some services
(XTE-150).

NFR
===

Database users
--------------

A component that uses the database MUST have at least two users in the
database (NFR 2.1)

Web interfaces compatibility with NFR
-------------------------------------

Web interfaces need to be checked for compatibility with NFR (NFR 4.\*).

Getting rid of unconfigured references
--------------------------------------

Components of X-Road MUST NOT use unconfigured (hard-coded) references
to files or external systems (NFR 5.2.1).

Package naming
--------------

Package naming must be in accordance with NFR 5.2.3.

SS/CS status json
-----------------

Output security server and central server status using json format (NFR
5.3.3).

Security Requirements document
------------------------------

Create Security Requirements document (NFR 6.1).
