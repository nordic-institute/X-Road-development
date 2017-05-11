

X-Road Joint Development
# Workflow Policy

v1.6

## 1	General

1.1	This document establishes workflow policy for joint development of X-Road software. Workflow Policy strives to serve as a handbook for all practical aspects of development.

1.2	Workflow is understood as systematic arrangement of work, a complex of processes, practices, roles and responsibilities, communication patterns, and artefacts.

1.3	Goals of the workflow policy are to
- establish productive and secure collaborative open source working environment
- assure production of high quality software
- avoid duplication of effort, facilitate re-use of software
- transparency and openness
- broader community of developers
- use of software development best practice
- clear communication among Partners as well as other stakeholders in the X-Road development process
- innovation.

1.4 This policy uses terminology of [X-Road Joint Development Charter](https://github.com/vrk-kpa/xroad-joint-development/blob/master/CHARTER.md).

1.5 Adherence to this policy are made legally binding to Vendors by inclusion of appropriate stipulations in contracts between Partners and Vendors. Vendor in context of this policy is a firm or other organisation performing development work by assigment of a Partner.

1.6 Partners and Developers implement this policy in good faith and in the context of sustainable, good software development practice.

1.7 Projects may have their own workflow arrangements as far as these do not contradict this policy.

## 2 Related documents

2.1 Workflow policy is related to other X-Road joint development policy and regulations:
- workflow policy implements the higher-level agreements of [X-Road Joint Development Charter](https://github.com/vrk-kpa/xroad-joint-development/blob/master/CHARTER.md)
- developments are co-ordinated by [X-Road Joint Development Roadmap](https://github.com/vrk-kpa/xroad-joint-development/blob/master/ROADMAP.md)
- technical consistency of X-Road software is maintained with help of [X-Road Non-Functional Requirements](https://github.com/vrk-kpa/xroad-joint-development/blob/master/NFR.md).

See also other documentation in [X-Road Joint Development](https://github.com/vrk-kpa/xroad-joint-development) repository.

## 3 Development model

3.1	X-Road uses [Github](https://github.com/) and [Git](https://git-scm.com/) based version management. In general the workflow policy follows Atlassian [Gitflow](https://www.atlassian.com/git/tutorials/comparing-workflows#gitflow-workflow) scheme but instead of working directly in the ria-ee/X-Road main repository the development is done in forked repositories. The main forks at the time being are vrk-kpa/X-Road and cybernetica-xroad/X-Road. [Semantic versioning](http://semver.org/) scheme is used for software versions.

## 4	Repositories

4.1	The following code and documentation repositories are used:
- Master Repository - short name: `X-Road`; hosted by: GitHub; managed by: RIA; purpose: release of X-Road software; access: Head Architect has write access; read access: ALL.
- Master Test Repository - short name: `X-Road-tests`; hosted by: GitHub; managed by: RIA; purpose: release of X-Road automated tests; access: Head Architect has write access; read access: ALL.
- Vendor repositories - purpose: development work carried out by Vendor; administered by: Vendor.

4.2	Partners can establish their own, additional repositories, for backup, software distribution or other purposes.

## 5	Branching pattern

5.1	Branching pattern follows the [Gitflow model](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow). Two perpetual branches – `master` and `develop` – together with three additional branches – `feature`, `release` and `hotfix` – are used.

- `master` branch is used to release X-Road software into production
- `develop` branch is used to accumulate features for the next big release
- `feature` branches are used to work on features (or closely related sets of features) to enhance X-Road core software
- new production release is prepared on `release` branch
- patches are prepared on `hotfix` branches.

## 6 Tagging

6.1 The versions merged to `X-Road/master` branch are tagged by Head Architect with annotated tags. E.g.

`git tag -a 6.7.12 -m "X-Road 6.7.12"`

The versions merged to `X-Road/develop` branch are not tagged.

## 7 Package naming

7.1 There are development versions and release versions and their package naming format is different.

7.2 The development package name format is `X.Y.Z-R.YYYYMMDDHHMMSSgitAAAAAA` (e.g. xroad-securityserver_6.14.0-0.20170428110816gitfbe4542_all.deb and xroad-securityserver-6.14.0-0.20170428110816gitfbe4542.el7.noarch.rpm)
- The software version X.Y.Z: X=major, Y=minor, Z=bugfix, e.g. 6.7.1
- R=package release number. For development versions this should be set to 0.
- YYYYMMDDHHMMSS = git commit timestamp (UTC) and AAAAAA = git commit hash (git show -s --format=%h)
  - The purpose of the timestamp is to ensure that packages will update although the software version number is not changed
  - Commit hash can be used to help working out from which commit the packages are made of

7.3 The release package name format is `X.Y.Z-R` (e.g. xroad-securityserver_6.14.0-1_all.deb and xroad-securityserver-6.14.0-1.noarch.rpm)
- R=package release number. If there is no specific reason to set otherwise, for release versions it should be equal to 1 (debian/rhel convention)
  - Specific reason to raise the package release number could be a bug in packaging when the software version doesn't change, only packaging. When the software version changes, the package release number is set back to 1.

## 8 Changelog management

8.1 The main changelog of the application is in [CHANGELOG.md](https://github.com/ria-ee/X-Road/blob/develop/CHANGELOG.md) and it contains all software changes. The changelog entry format is

```
## X.Y.Z - YYYY-MM-DD
- ISSUE: Description.
```

For example

```
## 6.12.0 - 2017-03-13
- XTE-99 / Joint development issue #79: Security Server UI: Added uniqueness check of the entered security server code when initializing the server.
- XTE-252 / Joint development issue #53: Security Server: Upgraded embedded Jetty to the version 9.4.2. Due to upgrade SHA1 ciphers are no longer supported for communication between security server and client.
- XTE-293: Security Server: A field set used to generate the token ID of the SSCD has been made configurable.
- XTE-294 / Joint development issue #84: Security Server: Added configuration file for the OCSP responder Jetty server (and increased max threads size of the thread pool).
- XTE-307 / Joint development issue #131: Security Server bugfix: Added missing HTTP header "Connection: close" into the server proxy response in cases error occurs before parsing a service provider's response.
- XTE-308 / Joint development issue #132: Security Server bugfix: Added missing read timeout for OCSP responder client.
- XTE-310 / Joint development issue #125: Security Server bugfix: SOAP messages with attachments caused in some cases a temopray file handle leak.
- XTE-333 / Joint development issue #128: Security Server bugfix: Fixed parsing SOAP messages containing &amp; or &lt; entities.
- Security Server: TCP socket SO_LINGER values in the proxy configuration file (proxy.ini) set to -1 according to avoid unexpected data stream closures.
```

Debian packaging has its own changelogs in `src/packages/xroad/debian/changelog` and `src/packages/xroad-jetty9/debian/changelog` but these are not used to record changelog entries since these are already in [CHANGELOG.md](https://github.com/ria-ee/X-Road/blob/develop/CHANGELOG.md), only to set the Debian package version. I.e. the following Debian changelog is sufficient.

```
xroad (6.14.0-0) trusty; urgency=medium
  * Change history is found at /usr/share/doc/xroad-securityserver/CHANGELOG.md
-- Jarkko Hyöty <jarkko.hyoty@gofore.com> Tue, 11 Apr 2017 15:46:12 +0300
```

## 9 Pull requests

9.1 Pull requests from Partners made against the `X-Road/develop` branch MUST follow these conventions
- Pull request name format is `country-version-sequence` e.g. Finnish-6.15.0-3
  - Country=origin of the pull request
  - Version=version of the software this pull request is intended for
  - Sequence=sequence number of the pull request. There can be multiple pull requests aiming for the same release and the sequence distinguishes between these.
- Description field must contain at least the changelist. Any relevant additional information should also be provided here.

Release and hotfix pull requests made against `master` branch must follow these conventions
- Pull request name format is just `version` e.g. 6.15.0
- Description field must contain at least the changelist. Any relevant additional information should also be provided here.

9.2 To ease the review work and to make clearer what changes are done, the following guidelines are required:

- Separate commits MUST be made for every bug fix included to pull request
- Separate commits SHOULD be made for every feature included to pull request

One pull request can contain several bug fix or feature commits. However, pull requests containing critical production related bug fixes should be keep simple to make reviewing easier.

9.3 For commit messages the following format SHOULD be used:

`ISSUE-111: Fix typo in security server user guide`

## 10 Work initiation

10.1 New development is initiated by preparing an enhancement proposal. The proposal is submitted for review and approval to X-Road Joint Development Steering Committee, according to the procedure in [X-Road Joint Development Charter](https://github.com/vrk-kpa/xroad-joint-development/blob/master/CHARTER.md), section "Scoping Process".

10.2 Partners co-ordinate development by [X-Road Roadmap](https://github.com/vrk-kpa/xroad-joint-development/blob/master/ROADMAP.md). Approved proposal will be entered into [Roadmap](https://github.com/vrk-kpa/xroad-joint-development/blob/master/ROADMAP.md). Dependencies and effects to other components of the X-Road software and other projects must be analysed in preparing of proposals.

10.3	Vendors develop software in their repositories, on `feature` branches.

Procedure:
- Vendor creates its vendor repository by forking `X-Road`.
- Vendor creates `feature` branch in vendor repository by branching from `develop`.

10.4 **Vendor version numbering.** To distinguish vendor-specific work, Vendor can label its product by attaching vendor suffix and vendor version number to X-Road semantic version number. Example: `6.8.0-0.AcmeCorp.3` denotes software developed by Acme Corporation, version 3.

## 11	Performing and integrating work

11.1 X-Road is collaboratively developed by the X-Road Partners. The Vendors working for the Partners have forked X-Road and the development work is done in the fork. Partners coordinate towards a common release by assigning tasks to Vendors that constantly integrate their work to the main repository. Vendor is required to periodically fetch updates from `X-Road/develop` and integrate into Vendor's branch as described in [Github's documentation](https://help.github.com/articles/syncing-a-fork/). The purpose of this is to facilitate merging of Vendor's work into `X-Road/develop`.

11.2 It is the responsibility of the Contracting Partner to notify the Vendor about new development added to Roadmap that might affect Vendor's development responsibilities.

## 12 Submitting and accepting work

12.1 Upon completion of feature development, Vendor submits a pull request to `X-Road/develop`. Prior to submitting the request Vendor must fetch the most recent updates from `X-Road/develop` and integrate into Vendor's branch (solve conflicts, if any). In practise when integration is due a `release` branch is forked out of `develop` in the Vendor's fork. In the `release` branch the code is developed and tested until it is ready to be taken forward. Once the code is ready a pull request is made from the fork's `release` branch to the `X-Road/develop` branch as described in the [Github documentation](https://help.github.com/articles/creating-a-pull-request-from-a-fork/). If defects are found in the pull request review they are fixed in the fork's `release` branch and the Github pull request updates automatically. When the pull request is eventually accepted to `X-Road/develop` the changes are synced back to fork's `develop` as described in the [Github documentation](https://help.github.com/articles/syncing-a-fork/).

![X-Road Integration](IMG/xroad-integration.png)

12.2	The pull request is reviewed by Head Architect and selected representative of each Partner. Additional reviewers can be added as necessary. The pull request is reviewed according to the acceptance criteria that was in effect when the work on this changeset started.

12.2.1 Feature analysis

- Are the features OK to be accepted to the core?
- The feature should come through the change management process and be accepted by one of the product owners.

12.2.2 Source code

- Is the source code for the software and its dependencies available?

12.2.3 Non-functional requirements

- Does the code conform to the X-Road non-functional requirements (see [X-Road Non-Functional Requirements](https://github.com/vrk-kpa/xroad-joint-development/blob/master/NFR.md))?

12.2.4 Version number

- Is the version number format correct (see https://github.com/vrk-kpa/xroad-joint-development/blob/master/CHARTER.md)?
- Is the version number correct (as agreed on the roadmap)?

12.2.5 CI build & tests

- No merge conflicts?
- Does the build and the test cases work?
- Does the packaging work (Ubuntu & RHEL)?
- Can the software be installed on a clean system (Ubuntu & RHEL)?
- Can the software version be upgraded from the previous `X-Road/master` version?

12.2.6 SonarQube (LTS) static analysis

- Is there enough test coverage? The test coverage should be equal or higher than in the previous version.
- SonarQube shows no bugs or code smells of severity blocker or critical? The developer has a chance to comment the issues before accept/reject action.

12.2.7 Changelogs

- Have the changelogs been updated and include the changes made?
- The changelog items contain reference to the backlog item where applicable?

12.2.8 Licensing

- Is the code licensing OK?

12.2.9 Documentation

- Has the documentation been updated?
- Is the documentation in correct format as specified in [X-Road Formatting & Style Guide](https://github.com/vrk-kpa/xroad-joint-development/blob/master/FormattingStyleGuide.md)? Are the sources of pictures provided?

12.3 Pull requests are generally reviewed and accepted on first-come, first-served (FCFS) basis.

12.4 If acceptance criteria are not met, then Vendor is requested to bring submitted work up to acceptance requirements.

12.5 Head Architect can, in consultation with Partners, hold up acceptance of new pull requests from other Vendors, to allow Vendor fix the deficiencies found in submitted work.

12.6 In cases of justified need, developers can request for up to 2 week 'code freeze' in `develop` branch of X-Road from Head Architect.

12.7 Up to 4 week 'code freeze' period can be applied to `X-Road/master` by approval of Head Architect.

12.8 When the changeset meets the acceptance criteria and all the reviewers have accepted the work, then Head Architect pulls in and merges the work into `X-Road/develop`.

## 13	Release preparation

13.1	Once enough features have accumulated to `X-Road/develop` branch the X-Road Steering Committee can decide to make a release. First a `release` branch is forked from the `develop` branch and pull request is made against `X-Road/master`. The version in the `release` branch is then exhaustively tested and fixes are made when necessary. When the version in the `release` branch satisfies all X-Road partners the `release` branch is merged to `master`.

![Release preparation](IMG/xroad-release.png)

13.2	Jointly developed X-Road software is released by the procedure:

-	Vendor creates a `release` branch from `develop` and makes a pull request against `X-Road/master`.
- both Partners thoroughly review the software to be released.
- Steering Committee decides to release, including the version number (see [X-Road Joint Development Charter](https://github.com/vrk-kpa/xroad-joint-development/blob/master/CHARTER.md), sections “Release sequence” and “Version compatibility”).
- Head Architect merges the pull request from `release` branch into `X-Road/master` and tags the commit with version number.
- Head Architect also updates `X-Road/develop` with changes made on `release` branch.

## 14	Deployment

14.1	Partners can fetch released software into Partner repositories. Partner repositories serve as distribution points for Partner country organisations.

## 15	Hotfix

15.1	Critical bug in production version is handled by preparation and release of a patch (see [X-Road Joint Development Charter](https://github.com/vrk-kpa/xroad-joint-development/blob/master/CHARTER.md), section “Warranty”).

15.2	Vendor prepares a patch on `hotfix` branch forked from the `master` branch in forked repository.

![Hotfix](IMG/xroad-hotfix.png)

15.3	When the fix is ready a pull request is made against the `X-Road/master` branch. If defects are found in the pull request review they are fixed in the `hotfix` branch. After the pull request has been accepted the changes can be merged to `X-Road/develop` and synced back to forked repository.

15.4 Hotfix can also be made for `develop` branch the same way as described for `master` branch above. This situation is possible if after an integration made to `X-Road/develop` branch a partner requests a fix/change to previous.

## 16	Setting up repositories

16.1	Repositories are set up according to the process:

- Head Architect sets up the Master Repository `X-Road`. Repository is initialised by committing X-Road v6.0 software into the `master` branch.
- Head Architect creates `develop` branch in `X-Road`.

## 17	Open source development

17.1	Open source development and Partner development are only loosely coupled. Master Repository `X-Road` is open to everybody for forking. RIA administers the Master Repository `X-Road`, in consultation with VRK.

17.2	New branches are created in `X-Road` by Manager of `X-Road` as needed.

17.3	Pull requests into `X-Road` are reviewed and accepted by Manager of `X-Road`.

17.4	Good quality and useful results of open source development can be integrated into `X-Road`. Exact procedure is out of scope of this document.

## 18	Documentation policy

18.1	X-Road joint documentation is produced in English. Partners are free to translate documentation into national languages.

18.2	Production format for documentation is [GitHub Flavoured Markdown](https://help.github.com/articles/github-flavored-markdown/).

18.3	Partners can publish X-Road documentation on their own websites, either verbatim or in part. Partners can modify and extend the documentation as they consider fit for their uses.

## 19	Approval, publication and amendment

19.1	Workflow will be amended as needed. Amendments are guided by the goal of having efficient and flexible workflow.

19.2  All participants of the development can propose to amend Workflow Policy. Amendment proposal can be submitted by raising an issue or submitting a pull request in GitHub.

19.3	Head Architect, upon consultation with Partners, when appropriate, accepts or rejects the proposal.

19.4	Current version of Workflow Policy is made public in GitHub, https://github.com/vrk-kpa/xroad-joint-development/blob/master/WORKFLOW.md.

## 20 Testing

20.1	All test scripts and software is published in X-Road-tests.

20.2 The branching pattern and workflow with X-Road-tests is the same as with X-Road.

20.3 For clarity X-Road-tests is divided into 3 folders - COMMON, EE-NATIONAL and FI-NATIONAL. National folders are dedicated for national implementation only tests.
