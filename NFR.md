X-Road Non-Functional Requirements v1.1
========================================

Introduction
------------

This document reflects the X-Road agreements on X-Road Non-Functional
Requirements (X-Road NFR), which define the concepts of a "good
software".

This X-Road NFR document is released in the public github repository
<https://github.com/vrk-kpa/xroad-joint-development> and all changes to
X-Road NFR will be proposed, discussed, and agreed on using github issues.

References
----------

[ARC-G] X-Road architecture document

[SPEC-AL] X-Road audit log events document

Scope
-----

The following requirements are intended for X-Road core functionality
that is specified in X-Road architecture document \[ARC-G\].

A term “application” in this document is used to describe the whole X-Road
core software being developed or improved.

A term “component” in this document is used to describe the software
components of X-Road as defined in X-Road architecture document \[ARC-G\].
For example Central Server and Security Server are X-Road components.

A term “subcomponent” in this document is used to describe subcomponents of
X-Road components. For example Proxy and Signer are subcomponents of X-Road.

A term “third party component” in this document is used to describe libaries
and programs that X-Road application depend on.

The scope of changes to application must be defined in procurement
documents. Only the added or changed portions of the software must
comply to the following requirements unless specified otherwise.

Architecture
------------

1.1 Application interfaces must be implemented in a secure way so that
faults of external systems could affect only directly related use cases.

1.2 The application must be divided into components in accordance with
the logical division. The resulting components must be deployed
separately. For example Security Server must be deployed separately from
Central Server.

1.3 Application and databases must use UTF-8 encoding.

1.4 Application must be able to handle timezones correctly.

1.5 Application must be implemented for both Ubuntu LTS 14.04 and Redhat
RHEL 7 platform.

1.6 Application must be able to communicate with the network using IP v4
protocol.

1.7 Third party components used must not restrict sublicensing and
distribution with MIT license.

1.8 None of the third party components used may result in financial
obligations for X-Road users.

Relational database
-------------------

2.1 A component that uses the database must have at least two users
in the database:

a\) A user (for example &lt;Component&gt;) who is the owner of the
database and all the objects within that database. This user is used for
software installations.

b\) A restricted user (for example &lt;Component&gt;\_app) who has
rights (SELECT, INSERT, UPDATE, DELETE) to execute only permitted
operations in that database. This user is used by component for normal
access to database.

Note: Current X-Road implementation is not yet compatible with
requirement 2.1.

2.2 It is obligatory to use Foreign Keys for referencing data from one
table to an other.

2.3 All Foreign Keys must be indexed.

2.4 All tables in the database must have exactly one Primary Key of
integer type. Primary key must be surrogate key which means fields
related to real life must not be used as primary keys.

2.5 All Primary Keys must be indexed using unique index.

2.6 If database contains data with high integrity requirement, then it
is obligatory to keep versioning history of such data.

2.7 The length of the database fields in DDL (Data definition language)
must be described in symbols, not in bytes.

2.8 It is obligatory to use variable binding in database queries.

2.9 The names of the database objects must be in English. The names may
contain only lower case Latin1 (ISO 8859-1) characters "a-z", numbers
"0-9" and underscores "\_". The names of objects must not begin with
numbers. The names of database objects need to be semantically
meaningful (open up the meaning of the object). In case if database
system does not support small characters for object names then it is
allowed to use capital characters.

2.10 The components must be agnostic to table partitioning
(<http://en.wikipedia.org/wiki/Partition_%28database%29>).

Source code
-----------

### General

3.1.1 Application must be equipped with the unit tests.

3.1.2 Source code, comments, documentation, and log messages must be in
English throughout.

3.1.3 Source Code must be marked with licensing information according to
MIT license rules. Copyright must be clearly defined.

3.1.4 New X-Road components must be created using Java 8 SE.
Additionally JRuby may be used for web interfaces.

### Java

3.2.1 Checkstyle (<http://checkstyle.sourceforge.net/>) must not issue any
errors with the configuration defined in
<https://github.com/vrk-kpa/xroad-public/blob/master/src/doc/checkstyle.xml>.

3.2.2 PMD (<http://pmd.sourceforge.net/>) must not issue any errors with the
configuration defined in
<https://github.com/vrk-kpa/xroad-public/blob/master/src/build.gradle>.

3.2.3 All libraries needed for the operation of the component must be
located in /lib directory of the same component.

3.2.4 Each release of application may contain only the necessary libraries
and there can be only one version of each library. All library dependencies
must be described in Gradle build files. Using external libraries without
dependencies description is not permitted.

3.2.5 If a new improved functionality requires a newer library version
then it is obligatory to update whole application to use that newer
library version.

### Changelog

3.3.1 The developer must supply a human readable commit message with
every commit. Commit messages must describe in human readable form
functionality changes.

### JRuby

3.4.1 Rubocop (<https://github.com/bbatsov/rubocop>) must not issue any
errors or warnings in ruby/jruby functions with the default
configuration (rubocop --fail-level warning).
Rubocop (<https://github.com/bbatsov/rubocop>) must not issue any errors
with the configuration defined in
<https://github.com/vrk-kpa/xroad-public/blob/master/src/check_ruby_source.sh>.

### JavaScript

3.5.1 JavaScript code must comply to Google JavaScript style guide
(<https://google.github.io/styleguide/javascriptguide.xml>).

Web interfaces
--------------

Note: Current X-Road implementation had not yet been checked for
compatibility with web interfaces requirements.

4.1 The styles that application uses must be located in separate CSS
files, that means HTML style elements and style attributes can not be
used.

4.2 The system must use deeplinking. Each page should have a unique,
automatically generated and human-readable web address (URL), and it
should not be linked to a users session or a users sensitive personal
data.

4.3 The system must replace the default error page, while preserving the
original HTTP response code.

4.4 Interface must conform to HTML 5 and CSS 3 standards.

4.5 Only web features supported by the majority of the web browsers may
be used for building web interfaces. Web interfaces must be fully
operational in the latest stable versions of the following web browser
engines: Blink (tested with Chrome browser), Gecko (tested with Firefox
browser), EdgeHTML (tested with Edge browser), Trident (tested with
Internet Explorer 10 and 11) and WebKit (tested with Safari for OS X 8
and 9). Testing of this requirement is performed using browser versions
that were latest stable at some point of development phase. Developer
may chose any operating system for testing of cross-platform engines.

4.6 If the interface is not compatible with the browser used, the user
should be notified.

Management
----------

### General

5.1.1 The component is allowed to directly alter the system (modify
environmental variables, create files in the local file system, etc)
containing that component only if functional requirements state so.
All such alterations must be fully documented. The secondary effects to
the system such as logs written by SLF4J are allowed.

5.1.2 The component is allowed to send e-mails only through an
external mail agent (for example, postfix).

5.1.3 All distributed components of the application must be packaged as
both deb and rpm files. Source code must be supplemented with scripts
required for building deb and rpm packages.

### Installation and settings

5.2.1 The component must not use unconfigured (hard-coded) references
to files or external systems.

Note: Current X-Road implementation is not yet compatible with
requirement 5.2.1.

5.2.2 Application building and unit testing must be automated with
Gradle. Application packaging must me automated with a script.
Components installation, update, and removal must be automated with
both DEB and RPM systems.

5.2.3 Package names may contain only the characters \[a-Z0-9\], “-”, “.”
and “\_”. DEB package name must include the project name, version, build
time, and architecture (for example
xroad-proxy\_6.8.3-0-201510281010\_all.deb). RPM package name must
include the project name, version, and build time (for example
xroad-proxy\_6.8.3-1-201510281010.rpm).

Note: Current X-Road implementation is not yet compatible with
requirement 5.2.3.

5.2.4 Component installation must not require different database users
then these described in section 2.1.

### Monitoring

5.3.1 Application Logging must be organized using standard tools in a
way that allows the application administrator to define and modify the
logs output (at least the file, database, syslogd), logging levels, and
logging format.

5.3.2 Java components must use SLF4J framework (see http://www.slf4j.org).

5.3.3 Every component of the system that has web interface must report in
machine-readable form its name, version number, status of essential
external systems, time of last execution, time of components package
creation and current server time. For example such report may be issued
at /heartbeat.json location.

Note: Current X-Road implementation is not yet compatible with
requirement 5.3.3.

5.3.4 Logs are written in English (except for the localized notices
shown to users).

5.3.5 All web servers must produce access.log files in a standard
format.

5.3.6 Calling methods of other components must result in debug level
logging of all input parameters and return values.

Information Security
--------------------

6.1 Application must confirm to Security Requirements document.

Note: Security Requirements document is not yet created. Current X-Road
implementation therefore is not yet compatible with requirement 6.1

6.2 The application must not create a new authentication system.
Authentication must be based on existing core OS systems (PAM, Kerberos,
etc.).

6.3 Both session creation and termination must be simultaneous for all
application layers. Session length must not be infinite.

6.4 Exiting the system must be made in a secure manner, explicitly and
comprehensibly to the user. The user can exit the system in two ways:
his sessions length is longer than the set values (separately definable
limits for the session length and the period of inactivity) or user
terminates the session on his own initiative.

6.5 Events critical from security point of view and activities that can
lead to financial or legal consequences must be logged in the separately
configurable audit log. List of these events can be found in X-Road
audit log events document \[SPEC-AL\].

6.6 All outputs must be sanitised not to include system operation information
such as full names of files, stack traces, etc.

6.7 In web interfaces session management must be based on session cookies.

6.8 All private network communications (excluding localhost) must be protected
with TLS. All public network communications must be protected with either TLS
or data signing (like for example signed global configuration). TLS parameters
must be configurable by administrator, not developer.

6.9 User must receive a proper informative message about termination of his
session.

6.10 Application must use strong encryption algorithms. All algorithms must
be approved by some cryptographic research. For example: [Estonian cryptographic
algorithms research 2015](https://www.ria.ee/public/RIA/Kruptograafiliste_algoritmide_uuring_2015.pdf) 


Standards
---------

7.1 The processing of the date, combined date and time, time, duration,
and the time interval in the text form must be based on the
international standard ISO 8601
(<https://en.wikipedia.org/wiki/ISO_8601>).

7.2 Only Linux/Unix (LF; 0x0A; U+000A) newline convention is allowed in
source code files.

7.3 All English texts must use United States (en\_US) dialect.
