

X-Road Joint Development
# Workflow Policy

v1.4

##1	General

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

1.5 Adherence to this policy are made legally binding to Vendors by inclusion of appropriate stipulations in contracts between between Partners and Vendors. Vendor in context of this policy is a firm or other organisation performing development work by assigment of a Partner.

1.6 Partners and Developers implement this policy in good faith and in the context of sustainable, good software development practice.

1.7 Projects may have their own workflow arrangements as far as these do not contradict this policy.

##2 Related documents

2.1 Workflow policy is related to other X-Road joint development policy and regulations:
- workflow policy implements the higher-level agreements of [X-Road Joint Development Charter](https://github.com/vrk-kpa/xroad-joint-development/blob/master/CHARTER.md)
- developments are co-ordinated by [X-Road Joint Development Roadmap](https://github.com/vrk-kpa/xroad-joint-development/blob/master/ROADMAP.md)
- technical consistency of X-Road software is maintained with help of [X-Road Non-Functional Requirements](https://github.com/vrk-kpa/xroad-joint-development/blob/master/NFR.md).
 
See also other documentation in [X-Road Joint Development](https://github.com/vrk-kpa/xroad-joint-development) repository.

##3 Development model

3.1	X-Road development uses the collaborative model based on [Git](https://git-scm.com/) distributed version control system.

##4	Repositories

4.1	The following code and documentation repositories are used:
- Master Repository - short name: `XM`; hosted by: GitHub; managed by: RIA; purpose: release of X-Road software; access: Head Architect has write access; read access: ALL.
- Master Test Repository - short name: `TM`; hosted by: GitHub; managed by: RIA; purpose: release of X-Road automated tests; access: Head Architect has write access; read access: ALL.
- Open Source Repository - short name: `XO`; hosted at: GitHub; purpose: open access publication of select parts of X-Road software; administered by: VRK; access: Head Architect has write access; everybody has read access.
- Vendor repositories - purpose: development work carried out by Vendor; administered by: Vendor.

4.2	Partners can establish their own, additional repositories, for backup, software distribution or other purposes.

## 5	Branching pattern

5.1	Branching pattern follows the Gitflow model [Gitflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow). Two perpetual branches – `master` and `develop` – together with three additional branches – `feature`, `release` and `hotfix` – are used.

- `master` branch is used to release X-Road software into production
- `develop` branch is used to accumulate features for the next big release
- `feature` branches are used to work on features (or closely related sets of features) to enhance X-Road core software
- new production release is prepared on `release` branch
- patches are prepared on `hotfix` branches.

##6 Work initiation

6.1 New development is initiated by preparing an enhancement proposal. The proposal is submitted for review and approval to X-Road Joint Development Steering Committee, according to the procedure in [X-Road Joint Development Charter](https://github.com/vrk-kpa/xroad-joint-development/blob/master/CHARTER.md), section "Scoping Process".

6.2 Partners co-ordinate development by [X-Road Roadmap](https://github.com/vrk-kpa/xroad-joint-development/blob/master/ROADMAP.md). Approved proposal will be entered into [Roadmap](https://github.com/vrk-kpa/xroad-joint-development/blob/master/ROADMAP.md). Dependencies and effects to other components of the X-Road software and other projects must be analysed in preparing of proposals.

6.3	Vendors develop software in their repositories, on `feature` branches.

![Feature Development](IMG/FeatureDevelopment.PNG)

Procedure:
- Vendor creates its vendor repository by forking `XM`.
- Vendor creates `feature` branch in vendor repository by branching from `XM/develop`.

6.4 **Vendor version numbering.** To distinguish vendor-specific work, vendor can label its product by attaching vendor suffix and vendor version number to X-Road semantic version number. Example: `6.8.0.AcmeCorp.3` denotes software developed by Acme Corporation, version 3.

##7	Performing work

7.1 Vendor is required periodically fetch updates from `XM/develop` and integrate into Vendor's branch. The purpose of this is to facilitate merging of Vendor's work into `XM/develop`.

7.2 It is the responsibility of the Contracting Partner to notify the Vendor about new development added to Roadmap that might affect Vendor's development responsibilities.

##8 Submitting and accepting work

8.1 Upon completion of feature development, Vendor submits a pull request to `XM/develop`. Prior to submitting the request Vendor must fetch the most recent updates from `XM/develop` and integrate into Vendor's branch (solve conflicts, if any) (see also previous item). 

8.2	The pull request is reviewed by Head Architect and selected representative of each Partner. Additional reviewers can be added as necessary. The pull request is reviewed according to the acceptance criteria that was in effect when the work on this changeset started.

8.2.1 Feature analysis

- Are the features OK to be accepted to the core?
- The feature should come through the change management process and be accepted by one of the product owners.

8.2.2 Source code

- Is the source code for the software and its dependencies available?

8.2.3 Non-functional requirements

- Does the code conform to the X-Road non-functional requirements(see [X-Road Non-Functional Requirements](https://github.com/vrk-kpa/xroad-joint-development/blob/master/NFR.md))?

8.2.4 Version number

- Is the version number format correct (see https://github.com/vrk-kpa/xroad-joint-development/blob/master/CHARTER.md)?
- Is the version number correct (as agreed on the roadmap)?

8.2.5 CI build & tests

- No merge conflicts?
- Does the build and the test cases work?
- Does the packaging work (Ubuntu & RHEL)?
- Can the software be installed on a clean system (Ubuntu & RHEL)?
- Can the software version be upgraded from the previous XM/source/master version?

8.2.6 SonarQube (LTS) static analysis

- Is there enough test coverage? The test coverage should be equal or higher than in the previous version.
- SonarQube shows no bugs or code smells of severity blocker or critical? The developer has a chance to comment the issues before accept/reject action.

8.2.7 Changelogs

- Have the changelogs been updated and include the changes made?
- The changelog items contain reference to the backlog item where applicable?

8.2.8 Licensing

- Is the code licensing OK?

8.2.9 Documentation

- Has the documentation been updated?
- Is the documentation in correct format?

8.3 Pull requests are generally reviewed and accepted on first-come, first-served (FCFS) basis.

8.4 If acceptance criteria are not met, then Vendor is requested to bring submitted work up to acceptance requirements.

8.5 Head Architect can, in consultation with Partners, hold up acceptance of new pull requests from other Vendors, to allow Vendor fix the deficiencies found in submitted work.

8.6 In cases of justified need, developers can request for up to 2 week 'code freeze' in develop branch of XM from Head Architect.

8.7 Up to 4 week 'code freeze' period can be applied to `XM/master` by approval of Head Architect.

8.8 When the changeset meets the acceptance criteria and all the reviewers have accepted the work, then Head Architect pulls in and merges the work into `XM/develop`. The commit is then tagged with version number.

## 9	Release preparation

9.1	New production release is prepared on `release` branch.

![Release preparation](IMG/ReleasePreparation.PNG)

9.2	Jointly developed X-Road software is released by the procedure:

-	Head Architect creates a `release` branch from `XM/develop`.
- both Partners thoroughly review the software to be released.
- Steering Committee decides to release, including the version number (see [X-Road Joint Development Charter](https://github.com/vrk-kpa/xroad-joint-development/blob/master/CHARTER.md), sections “Release sequence” and “Version compatibility”).
- Head Architect pushes software from `XM/release` into `XM/master` and tags the commit with version number.
- Head Architect also updates `XM/develop` with changes made on `release` branch.

9.3	New release also will be updated into X-Road Open Source repository (`XO`).	 

## 10	Deployment

10.1	Partners can fetch released software into Partner repositories. Partner repositories serve as distribution points for Partner country organisations.

## 11	Hotfix

11.1	Critical bug in production version is handled by preparation and release of a patch. 

11.2	Patch is prepared on `hotfix` branch.

![Hotfix](IMG/Hotfix.PNG)

11.3	Hotfix procedure:

- Head Architect creates a `XM/hotfix` branch from `XM/master`.
- A Partner is assigned to prepare a patch (see [Change Management Process], section “Warranty”).
- Partner, possibly using a Vendor, prepares the patch and commits it to `XM/hotfix`.
- Head Architect reviews the patch.
- Head Architect merges `XM/hotfix` into `XM/master` and tags the commit with version number.
- Head Architect merges changes made into `XM/hotfix` into `XM/develop`.	 

##12	Setting up repositories	

12.1	Repositories are set up according to the process:

- Head Architect sets up the Master Repository `XM`. Repository is initialised by committing X-Road v6.0 software into the `master` branch.
- Head Architect creates `develop` branch in `XM`.
- VRK creates repository `XO` and initialises it by committing X-Road v6.0 Security Server software and documentation into the repository.

## 13	Open source development

13.1	Open source development and Partner development are only loosely coupled. Open source repository `XO` is open to everybody for forking. VRK administers the open source repository `XO`, in consultation with RIA and X-Road Developer Community.

13.2	New branches are created in `XO` by Manager of `XO` as needed.

13.3	Pull requests into `XO` are reviewed and accepted by Manager of `XO`.

13.4	Manager of `XO` periodically updates `XO` with new content from `XM`.

13.5	Good quality and useful results of open source development can be integrated into `XM`. Exact procedure is out of scope of this document. 

## 14	Documentation policy

14.1	X-Road joint documentation is produced in English. Partners are free to translate documentation into national languages.

14.2	Production format for documentation is [GitHub Flavoured Markdown](https://help.github.com/articles/github-flavored-markdown/).

14.3	Partners can publish X-Road documentation on their own websites, either verbatim or in part. Partners can modify and extend the documentation as they consider fit for their uses.

## 15	Approval, publication and amendment

15.1	Workflow will be amended as needed. Amendments are guided by the goal of having efficient and flexible workflow.

15.2  All participants of the development can propose to amend Workflow Policy. Amendment proposal can be submitted by raising an issue or submitting a pull request in GitHub.

15.3	Head Architect, upon consultation with Partners, when appropriate, accepts or rejects the proposal.

15.4	Current version of Workflow Policy is made public in GitHub, https://github.com/vrk-kpa/xroad-joint-development/blob/master/WORKFLOW.md. 

## 16 Testing

16.1	All test scripts and software is published in TM

16.2 The branching pattern and workflow with TM is the same as with XM

16.3 For clarity TM is divided into 3 folders - COMMON, EE-NATIONAL and FI-NATIONAL. national folders are dedicated for national implementation only tests.
