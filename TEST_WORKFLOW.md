# Test Workflow Policy

#### VERSION CONTROL
| version no.	 | what has been done	| date/person
| ---- | ---- | ---- |
| ---- | ---- | ---- |
| 1.0	| Copied from X-Road Joint Development [repository](https://github.com/vrk-kpa/xroad-joint-development).	| 18.3.18 / PK
| 2.0 | Document updated to match the NIIS operating model. Changes approved by the Working Group. | 25.5.18 / PK
| 2.1 | Added chapter 1.9, updated chapter 5.1. | 31.5.18 / PK

## Table of contents

- [1	General](#1-general)
- [2 Related documents](#2-related-documents)
- [3 Development model](#3-development-model)
- [4	Repositories](#4-repositories)
- [5	Branching Pattern](#5-branching-pattern)
- [6 Tagging](#6-tagging)
- [7 Changelog Management and Pull Requests](#7-changelog-management-and-pull-requests)
- [8 Submitting and Accepting Tests Work](#8-submitting-and-accepting-tests-work)
- [9 Bug Fixes](#9-bug-fixes)

## 1	General

1.1	This document establishes workflow policy X-Road test development. Workflow
Policy strives to serve as a handbook for all practical aspects of development.

1.2	Workflow is understood as systematic arrangement of work, a complex of
processes, practices, roles and responsibilities, communication patterns, and
artefacts.

1.3	Goals of the workflow policy are to
- establish productive and secure collaborative open source working environment
- assure production of high quality software
- avoid duplication of effort, facilitate re-use of software
- transparency and openness
- broader community of developers
- use of software development best practice
- clear communication among Partners as well as other stakeholders in the X-Road test development process
- innovation.

1.4 This policy uses terminology of [X-Road Development Model](https://github.com/nordic-institute/x-road-development/blob/master/DEVELOPMENT_MODEL.md).

1.5 All the parties participating in the X-Road development must follow this
policy. This applies to the NIIS, the NIIS Members and X-Road community. In
case development work is ordered from a third party the organization conducting
the development is responsible for the inclusion of appropriate stipulations
in the contracts between the Contracting Party and the Vendor.

1.6 The NIIS, the NIIS Members and X-Road community implement this policy in good
faith and in the context of sustainable, good software development practice.

1.7 Projects may have their own workflow arrangements as far as these do not
contradict this policy.

1.8 In this document the NIIS Members and their contractors, and
X-Road community are referred as **Contributors**.

1.9 For clarity `nordic-institute/X-Road-tests` is divided into 3 folders -
COMMON, EE-NATIONAL and FI-NATIONAL. National folders are dedicated for national
implementation only tests.

## 2 Related documents

2.1 Workflow policy is related to other X-Road tests development policy and regulations:
- Harmonized X-road tests document [Harmonized X-Road test environment](https://github.com/ria-ee/blob/master/HARMONIZED_TEST_ENVIRONMENT.md)

## 3 Development model

3.1	X-Road uses [Github](https://github.com/) and [Git](https://git-scm.com/)
based version management. In general the workflow policy follows Atlassian [Gitflow](https://www.atlassian.com/git/tutorials/comparing-workflows#gitflow-workflow)
scheme.

* The NIIS developers are working directly in the `nordic-institute/X-Road-tests`
main repository.
* The NIIS Members may choose to work directly in the `nordic-institute/X-Road-tests`
main repository or in their own forked repository.
* X-Road community members work in their own forked repositories.

## 4	Repositories

4.1	The following code and documentation repositories are used:
- Master Test Repository - short name: X-Road-tests; hosted by: GitHub; managed by: NIIS; purpose: release of X-Road automated tests; access: NIIS has write access; read access: ALL.
- Contributor repositories - purpose: development work carried out by
Contributor; administered by: Contributor.

4.2	The Contributors can establish their own, additional repositories, for
backup, software distribution or other purposes.

## 5	Branching Pattern

5.1	The branching pattern used in the `nordic-institute/X-Road-tests`
repository is the same as in the `nordic-institute/X-Road` repository. Branching
pattern follows the [Gitflow model](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow). Two perpetual branches – `master` , `develop` and additional `feature` branches.

- `master` branch is used for release X-Road tests
- `develop` branch is used for test development
- `feature` branches are used to work on test features

Main repository:
- `master` branch https://github.com/rnordic-institute/X-Road-tests/tree/master
	- releases of X-Road-tests that correspond to a specific release of X-Road source code. Several versions of X-Road-tests may point to the same X-Road source code version if necessary.
	-  `master` branch releases are tagged with e.g "X-Road-tests for X-Road 6.16.0"
- `develop` branch https://github.com/nordic-institute/X-Road-tests/tree/develop
	- Integration branch between Finland and Estonia (and other possible partners)
	- Latest integrated test development source code

`README.md` file in the root of X-Road-tests must indicate the X-Road source code
version for both `master` and `develop` branches so that there is no confusion
for which version these tests were designated for. Indication is done by
pointing to the specific tag (master) or commit (develop) of the X-Road source
code.

## 6 Tagging

6.1 The versions merged to X-Road-tests/master branch are tagged by the NIIS.

`git tag -a 6.16.0 -m "X-Road-tests for X-road version 6.16.0"`

The versions merged to X-Road-tests/develop branch are not tagged.

## 7 Changelog management and Pull requests

Changelog description is visible in pull requests. Pull requests from
Contributors made against the `nordic-institute/X-Road-tests/master` or
`nordic-institute/X-Road-tests/develop` branch MUST follow these conventions:

- Pull request name format is 'contributor-month-year-description':
    - Contributor=origin of the pull request
    - Month=Month when the pull request was created
    - Year=Year when the pull request was created
    - Description=(short) Description of the pull request
        - e.g *Finnish-08-2017-Description-of-pull-request, Estonian-07-2017-Description-of-pull-request*
    - Description field must contain at least the changelist. Any relevant additional information should also be provided here.

## 8 Submitting and accepting tests work

8.1 Upon completion of tests development, submit a pull request to
`nordic-institute/X-Road-tests/develop`.

8.2	The pull request is reviewed by the NIIS. Additional reviewers can be
added as necessary. The pull request is reviewed according to the acceptance
criteria that was in effect when the work on this changeset started.

8.2.1 Source code

- Is the source code for tests and its dependencies available?

8.2.2 CI build & tests
- No merge conflicts
- Test must be working in LXC jenkins environment
- Tests must be attached to existing or new jenkins task
- Test must working reliably e.g executed multiple times
- If possible test must work independently

8.2.3 Documentation
- Is documentation updated?
- Changelog:
    - Version information
    - Notes for changes

8.2.4 Licensing
- License exists in root folder
- Is the licensing of the tests and its dependencies ok?

8.2.5 Browser acceptance testing
- Browser versions
    - Mozilla firefox version tests `README.md`
    - Chrome version version tests `README.md`
    	- Chrome used only smoke tests (excluding file download and upload, and
				certificates)

8.3 Pull request
- Pull requests are generally reviewed and accepted on first-come, first-served
(FCFS) basis.
- Descriptive git commit messages
	- E.g `Added xroad-global-configuration test case 3.3` or
	`Fixed login test working with new layout`

8.4 If acceptance criteria are not met, then Contributor is requested to bring
submitted work up to acceptance requirements.

8.5 The NIIS can, in consultation with the NIIS Members, hold up acceptance of
new pull requests from other Contributors, to allow a specific Contributor fix the
deficiencies found in submitted work.

8.6 When the changeset meets the acceptance criteria and all the reviewers have
accepted the work, then the NIIS pulls in and merges the work into
`nordic-institute/X-Road-tests/develop`.

## 9 Bug fixes

The NIIS is responsible for fixing software errors detected in the X-Road core
and providing second level support to the NIIS Members.
