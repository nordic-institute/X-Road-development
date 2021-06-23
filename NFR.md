# X-Road Non-Functional Requirements

#### VERSION CONTROL
| version no.	 | what has been done	| date/person
| ---- | ---- | ---- |
| 1.2	| Copied from X-Road Joint Development [repository](https://github.com/vrk-kpa/xroad-joint-development).	| 18.3.18 / PK
| 1.3	| Fixed link to `checkstyle.xml`, updated chapter 5.3 to "Git commit log".	| 31.5.18 / PK
| 1.4	| Minor updates.	| 23.06.21 / PK

## Table of contents

- [1	Introduction](#1-introduction)
- [2 Scope](#2-scope)
- [3 Architecture](#3-architecture)
- [4 Relational Database](#4-relational-database)
- [5 Source code](#5-source-code)
- [6 Web Interfaces](#6-web-interfaces)
- [7 Management](#7-management)
- [8 Information Security](#8-information-security)
- [9 Standards](#9-standards)
- [10 References](#10-references)

## 1 Introduction

This document reflects the X-Road agreements on X-Road Non-Functional
Requirements (X-Road NFR), which define the concepts of "good software".

This X-Road NFR document is released in the public GitHub repository
<https://github.com/nordic-institute/x-road-development> and all changes to
X-Road NFR MUST be proposed, discussed, and agreed on using GitHub issues.

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT",
"SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL"
in this document are to be interpreted as described in \[[RFC 2119](#Ref_RFC-2119)\].

## 2 Scope

The following requirements are intended for X-Road core functionality
that is specified in X-Road architecture document \[[ARC-G](#Ref_ARC-G)\].

A term “application” in this document is used to describe the whole X-Road
core software being developed or improved.

A term “component” in this document is used to describe the software
components of X-Road as defined in X-Road architecture document \[[ARC-G](#Ref_ARC-G)\].
For example Central Server and Security Server are X-Road components.

A term “third party component” in this document is used to describe libraries
and programs that X-Road application depends on.

The scope of changes to application MUST be defined in procurement
documents. Only the added or changed portions of the software MUST
comply with the following requirements unless specified otherwise.

## 3 Architecture

3.1 Application interfaces MUST be implemented in a secure way so that
faults of external systems could affect only directly related use cases.

3.2 The application MUST be divided into components in accordance with
the logical division. The resulting components MUST be deployed
separately. For example Security Server MUST be deployed separately from
Central Server.

3.3 Application and databases MUST use UTF-8 encoding.

3.4 Application MUST be able to handle time zones correctly.

3.5 Application MUST be implemented for the following platforms:

- Ubuntu LTS 18.04
  - Central Server, Configuration Proxy, Security Server
- Ubuntu LTS 20.04
  - Central Server, Configuration Proxy, Security Server
- Redhat Enterprise Linux (RHEL) 7
  - Security Server
- Redhat Enterprise Linux (RHEL) 8
  - Security Server.

3.6 Application MUST be able to communicate with the network using IP v4
protocol.

3.7 Third party components used MUST NOT restrict sublicensing and
distribution with MIT license.

3.8 Third party components used MUST NOT result in financial obligations
for X-Road users.

## 4 Relational database

4.1 A component that uses the database MUST have at least two users
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

4.2 It is REQUIRED to use Foreign Keys for referencing data from one
table to another.

4.3 All Foreign Keys MUST be indexed.

4.4 All tables in the database MUST have exactly one Primary Key of
integer type. Primary key MUST be surrogate key which means fields
related to real life MUST NOT be used as primary keys.

4.5 All Primary Keys MUST be indexed using unique index.

4.6 If database contains data with high integrity requirement, then it
is REQUIRED to keep versioning history of such data.

4.7 The length of the database fields in DDL (Data definition language)
MUST be described in symbols, not in bytes.

4.8 It is REQUIRED to use variable binding in database queries.

4.9 The names of the database objects MUST be in English. The names MUST
contain only lower case Latin1 (ISO 8859-1) characters "a-z", numbers
"0-9" and underscores "\_". The names of objects MUST NOT begin with
numbers. The names of database objects need to be semantically
meaningful (open up the meaning of the object). In case if database
system does not support small characters for object names then it is
allowed to use capital characters.

4.10 The components MUST be agnostic to table partitioning
(<http://en.wikipedia.org/wiki/Partition_%28database%29>).

## 5 Source code

### 5.1 General

5.1.1 Application MUST be equipped with the unit tests.

5.1.2 Source code, comments, documentation, and log messages MUST be in
English throughout.

5.1.3 Source Code MUST be marked with licensing information according to
MIT license rules. Copyright MUST be clearly defined.

5.1.4 New X-Road components MUST be created using Java 8 SE.

5.1.5 JRuby MUST NOT be used in any new components.

### 5.2 Java

5.2.1 Checkstyle (<http://checkstyle.sourceforge.net/>) MUST NOT issue any
errors with the configuration defined in
<https://github.com/nordic-institute/X-Road/blob/develop/src/config/checkstyle/checkstyle.xml>.

5.2.3 All libraries needed for the operation of the component MUST be either
packaged with the same component or component's installation package MUST
depend on appropriate library packages.

5.2.4 Each release of application MUST contain only the necessary libraries
and there MUST be only one version of each library. All library dependencies
MUST be described in Gradle build files. Using external libraries without
dependencies description is not permitted.

5.2.5 If a new improved functionality requires a newer library version
then it is REQUIRED to update whole application to use that newer
library version.

### 5.3 Git commit log

5.3.1 The developer MUST supply a human readable commit message with
every commit. Commit messages MUST describe in human readable form
functionality changes.

### 5.4 JRuby

5.4.1 Rubocop (<https://github.com/bbatsov/rubocop>) MUST NOT issue any
errors or warnings in ruby/jruby functions with the default
configuration (rubocop --fail-level warning).
Rubocop (<https://github.com/bbatsov/rubocop>) MUST NOT issue any errors
with the configuration defined in
<https://github.com/nordic-institute/xroad-public/blob/master/src/check_ruby_source.sh>.

### 5.5 JavaScript

5.5.1 JavaScript code MUST comply to Google JavaScript style guide
(<https://google.github.io/styleguide/javascriptguide.xml>).

## 6 Web interfaces

Note: Current X-Road implementation had not yet been checked for
compatibility with web interfaces requirements.

6.1 The styles that application uses MUST be located in separate CSS
files, that means HTML style elements and style attributes cannot be
used.

6.2 The system MUST use deep linking. Each page MUST have a unique,
automatically generated and human-readable web address (URL), and it
MUST NOT be linked to a user's session or a user's sensitive personal
data.

6.3 The system MUST replace the default error page, while preserving the
original HTTP response code.

6.4 Interface MUST conform to HTML 5 and CSS 3 standards.

## 7 Management

### 7.1 General

7.1.1 The component is allowed to directly alter the system (modify
environmental variables, create files in the local file system, etc.)
containing that component only if functional requirements state so.
All such alterations MUST be fully documented. The secondary effects to
the system such as logs written by SLF4J are allowed.

7.1.2 The component is allowed to send e-mails only through an
external mail agent (for example, postfix).

7.1.3 All distributed components of the application MUST be packaged as
both deb and rpm files. Source code MUST be supplemented with scripts
required for building deb and rpm packages.

### 7.2 Installation and settings

7.2.1 The component MUST NOT use unconfigured (hard-coded) references
to files or external systems.

7.2.2 Application building and unit testing MUST be automated with
Gradle. Application packaging MUST me automated with a script.
Components installation, update, and removal MUST be automated with
both DEB and RPM systems.

7.2.4 Component installation MUST NOT require different database users
then these described in section 2.1.

### 7.3 Monitoring

7.3.1 Application Logging MUST be organized using standard tools in a
way that allows the application administrator to define and modify the
logs output (at least the file, database, syslogd), logging levels, and
logging format.

7.3.2 Java components MUST use SLF4J framework (see <http://www.slf4j.org>).

7.3.3 Every component of the system MUST report its child component's ant its own hearbeat in machine-readable (JSON) form with a minimal dataset of:
* component name,
* version number with time of component's package creation,
* status of critical external systems/services,
* time of last successful execution,
* current server time.

7.3.4 Logs are written in English.

7.3.5 All web servers MUST produce access.log files in a standard
format.

## 8 Information Security

8.2 The application MUST NOT create a new authentication system.
Authentication MUST be based on existing core OS systems (PAM, Kerberos,
etc.).

8.3 Both session creation and termination MUST be simultaneous for all
application layers. Session length MUST NOT be infinite.

8.4 Exiting the system MUST be made in a secure manner, explicitly and
comprehensibly to the user. The user can exit the system in two ways:
his session's length is longer than the set values (separately definable
limits for the session length and the period of inactivity) or user
terminates the session on his own initiative.

8.5 Events critical from security point of view and activities that can
lead to financial or legal consequences MUST be logged in the separately
configurable audit log. List of these events can be found in X-Road
audit log events document \[[SPEC-AL](#Ref_SPEC-AL)\].

8.6 All user outputs MUST be sanitized not to include system operation information
such as full names of files, stack traces, etc.

8.7 In web interfaces session management MUST be based on session cookies.

8.8 All private network communications (excluding localhost) MUST be protected
with TLS. All public network communications MUST be protected with either TLS
or data signing (like for example signed global configuration). TLS parameters
MUST be configurable by administrator, not developer.

8.9 User MUST receive a proper informative message about termination of his
session.

8.10 Application MUST use strong encryption algorithms. All algorithms MUST
be approved by cryptographic research. For example: [Estonian cryptographic
algorithms research 2015](https://www.ria.ee/public/RIA/Kruptograafiliste_algoritmide_uuring_2015.pdf).


## 9 Standards

9.1 The processing of the date, combined date and time, time, duration,
and the time interval in the text form MUST be based on the
international standard ISO 8601
(<https://en.wikipedia.org/wiki/ISO_8601>).

9.2 Only Linux/Unix (LF; 0x0A; U+000A) newline convention is allowed in
source code files.

9.3 All English texts MUST use United States (en\_US) dialect.

## 10 References

1. <a id="Ref_ARC-G" class="anchor"></a>\[ARC-G\] X-Road architecture document, <https://github.com/nordic-institute/X-Road/blob/develop/doc/Architecture/arc-g_x-road_arhitecture.md>.

2. <a id="Ref_SPEC-AL" class="anchor"></a>\[SPEC-AL\] X-Road audit log events document, <https://github.com/nordic-institute/X-Road/blob/develop/doc/Architecture/spec-al_x-road_audit_log_events_1.7_Y-883-17.docx>.

3. <a id="Ref_RFC-2119" class="anchor"></a>\[RFC 2119\] Key words for use in RFCs to Indicate Requirement Levels, <https://www.ietf.org/rfc/rfc2119.txt>.
