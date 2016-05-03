# Backlog of Joint X-Road Development

## About

Backlog is a list of technical 'features' that are or will be developed to X-Road core technology.
Current document describes how backlog items are to be handled.

## Process

* Backlog items are issues in the xroad-joint-development repository.
* Items are named as user stories ("who", "where" and "what").
* New functionality is labeled as "enhancement".
* Issues that are fixes for existing functionality is labeled as "bug".
* Issues must have up to 1 label defining its status in the backlog: (no status label), "assigned", "wip", "done", "wont-fix". 
* Before initiating development activities the item must be described in backlog and achieve "assigned" or "wip" status from the workgroup.
  * Contributions from public domain are also handled following the same scheme - i.e. public domain contribution is not automatically accepted but rather sufficient understanding is built on the change and sheduled best time to merge it in the relation to other backlog items.
  * Critical patches can be made whan adding it to backlog, informing the workgroup and adding relevant information (see "assigned" status below) ASAP (Should we also label them? to make understanging of items that have not passed regular workgroup acceptance?).
* Issues are additionally labeled by decision of the workgroup as follows:
  * (no label) - proposed items that need discussion and decision in the workgroup. 
  * "assigned" - sufficiently described items that has an owener who will solve it. An "assigned" backlog item ("enchanement" or "bug") will have the folowing contents described:
    * Priority / Estimated development time
    * Estimated list of core components that are to be modified or created (follow the component architecture described in the architecture documents)
    * Estimation of documentation that is to be modified or created (follow the documentation masterlist found at ...)
  * "wip" - backlog item, that is being worked on. Must have an estimate delivery version/milestone. Must contain the following piece of information: the contact person who is dealing with the item. All other contributors are considered to be aware of the fact that mentioned components and documentation is changed and during this phase.
* Backlog items that are resolved will be closed and a status is assigned:
  * "wont-fix" - backlog items that are analyzed and found to be unneccessary and will not be fix nor new functionality added.
  * "done" - items that are merged to main development branch (see workflow for more details on branches). added version number and/or reference to the merged pull-request
* Relevant information is kept in the backlog issue description.

--------------------
# Old stuff

## General

General requirements.

#### SS ACL export/import
--------------------

Security server must support exporting and importing of access rights of
the services.

#### Shell scripts for executing meta-services
-----------------------------------------------

Create a simple command line scripts to execute management services.

#### Cost effective trust service consumption
----------------------------------------

Prefetching of OCSP must be configurable. When cost effective option is
selected then OCSP fetching should be executed only when needed.

#### Signature format documentation sufficiently described with examples to build external validators.
-------------------------------------------------------------------------------------------------

Create a better documentation of signature format used by X-Road and
provide that with examples. Documentation must be sufficient to build
external validators.

#### SS Hi-Availability
------------------

Create a new Hi-availability solution for clustering security servers
(needs researching first).

#### Log security
------------------

Log records need to be chained and timestamped.

#### Secure connection session timeout
------------------

Security servers currently cache secure connection sessions with other security servers.
This approach disables load balancing when a service is offered by multiple Security Servers.
It must be possible to configure security servers to periodically close sessions,
and try to establish new connection with a faster (less loaded) Security Server.

#### Automatic backup of configuration
------------------

Security and Central servers must be configured by default to periodically backup their configuration.

#### Message identifier unique check
------------------

There must be a background job that checks and notifies security server administrator
if message identifiers are not unique.

#### Automated joining with test X-road
------------------

It must be possible to configure (mainly for test environments) X-Road instance
to automatically accept new members, security servers, and subsystems without manual
insertion of these into central server.

## RIA JIRA

Requirements from RIA's JIRA.

#### CSR format of trust service provider
------------------------------------

It must be possible to save in X-Road center the preference for CSR
(certificate signing request) format for every trust service provider.
Generation of CSR in security server must automatically select the
correct format (XTE-187).

#### Subsystem full name
-------------------

Make it possible to add full name to subsystem. Full name should be
visible not only in the web interface of security and central servers,
but also in metaservices (XTE-149).

## VRK JIRA

Requirements from VRK's JIRA.

#### Ignore nextUpdate attribute on OCSP response validation

It must be possible to turn off ```nextUpdate``` attribute check on OCSP response validation and let ```ocspFreshnessSeconds``` parameter alone define the time period when OCSP response is considered valid. According to [RFC 6960](https://tools.ietf.org/html/rfc6960) it must be checked that nextUpdate value is in the future, otherwise the OCSP response is invalid. This may create problems if multiple CAs are used in the same X-Road instance or OCSP service is not available for period longer than ```ocspFreshnessSeconds```. (PVAYLADEV-364)

#### Signer Scalability
-------------------

The signer component must support parallel signing if multiple cores are available (PVAYLADEV-330).

#### Global configuration access
-------------------

The global configuration files distributed by the central server must be available for the proxy component through Security Server's in-memory cache (PVAYLADEV-350).

#### Serverconf
-------------------

Service related configuration (e.g. access rights) must be fetched from the database once per request at the maximum (PVAYLADEV-351). 

#### OCSP Response Verification
-------------------

Signing and authentication certificate's status must be verified once per request (PVAYLADEV-352).

## NFR

Non-functional requirements.

#### Database users
--------------

A component that uses the database MUST have at least two users in the
database (NFR 2.1)

#### Web interfaces compatibility with NFR
-------------------------------------

Web interfaces need to be checked for compatibility with NFR (NFR 4.\*).

#### Getting rid of unconfigured references
--------------------------------------

Components of X-Road MUST NOT use unconfigured (hard-coded) references
to files or external systems (NFR 5.2.1).

#### Package naming
--------------

Package naming must be in accordance with NFR 5.2.3.

#### SS/CS status json
-----------------

Output security server and central server status using json format (NFR
5.3.3).

#### Security Requirements document
------------------------------

Create Security Requirements document (NFR 6.1).
