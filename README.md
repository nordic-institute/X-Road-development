# X-Road Development

[![Go to X-Road Community Slack](https://img.shields.io/badge/Go%20to%20Community%20Slack-grey.svg)](https://jointxroad.slack.com/)
[![Get invited](https://img.shields.io/badge/No%20Slack-Get%20invited-green.svg)](https://x-road.global/join-the-xroad-community)

## Licence

This document is licensed under the Creative Commons Attribution-ShareAlike 3.0 Unported Licence. To view a copy of this licence, visit http://creativecommons.org/licenses/by-sa/3.0/

## Introduction

This repository is used for storing X-Road® development model, and
documentation regarding common development practices and guidelines.
It is also used for managing changes to these documents.

- [Development Model](DEVELOPMENT_MODEL.md)
- [Workflow](WORKFLOW.md)
- [NFR (Non-functional requirements)](NFR.md)

## X-Road Development 'Big Picture'

![](IMG/xroad_development.png)

The [Nordic Institute for Interoperability Solutions](https://niis.org) (NIIS)
owns the X-Road product and maintains Product Roadmap and Product Backlog. The
NIIS is responsible for:

* management, development, verification, and audit of the source code
* administration of documentation
* administration of business and technical requirements
* conducting development, and managing development tools, platforms and practices
* developing and implementing principles of licensing and distribution
* providing second-line support to NIIS members.

The **[NIIS Members](https://www.niis.org/organization-and-management/)**
nominate representatives to the **Advisory Group** and participate in the
**Working Group**. The NIIS organizes and facilitates Advisory Group and
Working Group meetings.

## X-Road Community

X-Road is released under the [MIT](https://en.wikipedia.org/wiki/MIT_License)
licence and is available free of charge for any individual or organization.
More information about the X-Road Community can be found
[here](https://x-road.global/community).

## How to contribute?

All contributions are warmly welcome. Submit a pull request, enhancement request,
error report or propose a change to the [Workflow](WORKFLOW.md). Requests are
reviewed in Working Group meetings and/or e-mail and/or issue comments.

### Pull requests

Pull requests can be submitted following the process described in the
[Workflow](WORKFLOW.md#12-submitting-and-accepting-work).

If a pull request implements a new feature or a bigger change in an existing feature, it's strongly recommended to submit an enhancement request in advance and indicate in the enhancement request that the implementation will be provided too. In that way, it's possible to ensure in advance that the pull request will be approved.

Also, in case you're planning to implement an existing backlog item, let NIIS know about your plans in advance to avoid duplicate work.

In case a pull request includes changes in the architecture, it's strongly recommended to discuss the changes with NIIS in advance. Agreeing on the details of the changes upfront will likely speed up the approval process.

### Enhancement requests and error reports

X-Road enhancement requests and error reports can be submitted to the [X-Road Service
Desk](https://jira.niis.org/servicedesk/customer/portal/1).
[Sign up](https://jira.niis.org/secure/Signup!default.jspa) for an account and
get access to the [X-Road Service
Desk](https://jira.niis.org/servicedesk/customer/portal/1) and
[X-Road Backlog](https://jira.niis.org/projects/XRDDEV/).

### Security issues and vulnerabilities

Security issues and vulnerabilities are reported privately to the [X-Road Service
Desk](https://jira.niis.org/servicedesk/customer/portal/1) using the
`Report a software problem` request type.
[Sign up](https://jira.niis.org/secure/Signup!default.jspa) for an account and
get access to the [X-Road Service Desk](https://jira.niis.org/servicedesk/customer/portal/1).

Another alternative to report security issues and vulnerabilities is the X-Road bug bounty program that is run on the Intigrity platform. [Visit the program details](https://app.intigriti.com/programs/niis/x-road/detail) to get started.

### Changes to the workflow

If you want to propose a change to the documents in this repository, please
[submit](https://github.com/nordic-institute/X-Road-development/issues/new) an
issue using the GitHub issue tracker.

### Contributor Licence Agreement

We appreciate community contributions to X-Road open source code repositories
managed by NIIS. By signing a [contributor licence agreement](https://en.wikipedia.org/wiki/Contributor_License_Agreement),
we ensure that the community is free to use your contributions.

#### Review the CLA document

The NIIS Contributor Licence Agreement (CLA) document is available as
a [Word](docs/NIIS_Contributor_Licence_Agreement.docx) and
[PDF](docs/NIIS_Contributor_Licence_Agreement.pdf) document.

#### Sign the CLA

When you contribute to X-Road open source project on GitHub with a new pull
request, it will be checked whether you have signed the CLA. If required, the
pull request will be commented on with further instructions. The CLA must be
received by NIIS prior to approval of the pull request. The CLA covers any and
all submissions that the contributor now, or in the future, submits to the
project. Therefore, it is enough to sign the CLA once before the first
contribution, and not with every contribution.

The CLA can be signed digitally using a
[qualified electronic signature](https://ec.europa.eu/cefdigital/wiki/display/CEFDIGITAL/Introduction+to+e-signature).
A digitally signed CLA must be emailed to `info@niis.org`.

Alternatively, the CLA can be printed out, signed manually and sent to NIIS
by post:

    MTÜ Nordic Institute for Interoperability Solutions
    Hobujaama 4
    10151 Tallinn
    Estonia

## Development Tools

The tools listed below are used in the development of the X-Road.

| URL | Description |
| --- | --- |
| https://jira.niis.org/projects/XRDDEV/ | X-Road backlog. |
| https://jira.niis.org/servicedesk/customer/portal/1 | X-Road Service Desk for submitting enhancement requests and error reports. |

[Sign up](https://jira.niis.org/secure/Signup!default.jspa) for an account and
get access to the tools.

More information about available X-Road developer resources is available
[here](https://x-road.global/resources).

## Source code

The X-Road core source code master repositories are listed below.

| Repository | Description |
| --- | --- |
| [nordic-institute/X-Road](https://github.com/nordic-institute/X-Road) | X-Road development repository. |
