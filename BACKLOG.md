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
