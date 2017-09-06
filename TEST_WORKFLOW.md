X-Road Tests development
# Workflow Policy

v1.0

## 1	General

1.1	This document establishes workflow policy for joint development of X-Road test development. Workflow Policy strives to serve as a handbook for all practical aspects of development.

1.2	Workflow is understood as systematic arrangement of work, a complex of processes, practices, roles and responsibilities, communication patterns, and artefacts.

1.3	Goals of the workflow policy are to
- establish productive and secure collaborative open source working environment
- assure production of high quality software
- avoid duplication of effort, facilitate re-use of software
- transparency and openness
- broader community of developers
- use of software development best practice
- clear communication among Partners as well as other stakeholders in the X-Road test development process
- innovation.

1.4 Adherence to this policy are made legally binding to Vendors by inclusion of appropriate stipulations in contracts between Partners and Vendors. Vendor in context of this policy is a firm or other organisation performing development work by assigment of a Partner.

1.5 Partners and Developers implement this policy in good faith and in the context of sustainable, good software development practice.

1.6 Projects may have their own workflow arrangements as far as these do not contradict this policy.

## 2 Related documents

2.1 Workflow policy is related to other X-Road tests development policy and regulations:
- Harmonized X-road tests document [Harmonized X-Road test environment](https://github.com/ria-ee/blob/master/HARMONIZED_TEST_ENVIRONMENT.md)

## 3 Development model

3.1	X-Road tests uses [Github](https://github.com/) and [Git](https://git-scm.com/) based version management.

## 4	Repositories

4.1	The following code and documentation repositories are used:
- Master Test Repository - short name: X-Road-tests; hosted by: GitHub; managed by: RIA; purpose: release of X-Road automated tests; access: Head Architect has write access; read access: ALL.
	- https://github.com/ria-ee/X-Road-tests

4.2	Partners can establish their own, additional repositories, for backup, software distribution or other purposes.

## 5	Branching pattern

5.1	Branching pattern follows the [Gitflow model](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow). Two perpetual branches – `master` , `develop` and own `feature` branches.

- `master` branch is used for release X-Road tests
- `develop` branch is used for test development
- `feature` branches are used to work on test features

Main repository:
- `master` branch https://github.com/ria-ee/X-Road-tests/tree/master
	- releases of X-Road-tests that correspond to a specific release of X-Road source code. Several versions of X-Road-tests may point to the same X-Road source code version if necessary.
	-  `master` branch releases are tagged with e.g "X-Road-tests for X-Road 6.16.0"
- `develop` branch https://github.com/ria-ee/X-Road-tests/tree/develop
	- Integration branch between Finland and Estonia (and other possible partners)
	- Latest integrated test development source code 

README.md file in the root of X-Road-tests must indicate the X-Road source code version for both `master` and `develop` branches so that there is no confusion for which version these tests were designated for. Indication is done by pointing to the specific tag (master) or commit (develop) of the X-Road source code.
	
	
Fork repository:
- `master` branch https://github.com/vrk-kpa/X-Road-tests and https://github.com/asaquality/X-Road-tests
	- Tagged releases of X-road-tests
- `develop` branch https://github.com/vrk-kpa/X-Road-tests and https://github.com/asaquality/X-Road-tests 
	- Latest country test development source code 
	- Make pull request to develop for ria-ee/X-Road-tests

## 6 Tagging

6.1 The versions merged to X-Road-tests/master branch are tagged by the Head Architect.

git tag -a 6.16.0 -m "X-Road-tests for X-road version 6.16.0"

The versions merged to X-Road-tests/develop branch are not tagged.

## 7 Changelog management and Pull requests

Changelog description is visible in pull requests. Pull requests from Partners made against the `ria-ee/X-Road-tests/master` or `ria-ee/X-Road-tests/develop` branch MUST follow these conventions:

- Pull request name format is 'country-month-year-description':
    - Country=origin of the pull request
    - Month=Month when the pull request was created
    - Year=Year when the pull request was created
    - Description=(short) Description of the pull request
        - e.g *Finnish-08-2017-Description-of-pull-request, Estonian-07-2017-Description-of-pull-request*
    - Description field must contain at least the changelist. Any relevant additional information should also be provided here.

## 8 Submitting and accepting tests work

8.1 Upon completion of tests development, submit a pull request to `ria-ee/X-Road-tests/develop`.

8.2	The pull request is reviewed by Finland and Estonia responsible persons. Additional reviewers can be added as necessary. The pull request is reviewed according to the acceptance criteria that was in effect when the work on this changeset started.

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
    - Mozilla firefox version tests README.md
    - Chrome version version tests README.md
    	- Chrome used only smoke tests (excluding file download and upload, and certificates)

8.3 Pull request
- Pull requests are generally reviewed and accepted on first-come, first-served (FCFS) basis.
- Descriptive git commit messages
	- E.g *"Added xroad-global-configuration test case 3.3"* or *"Fixed login test working with new layout"*

8.4 If acceptance criteria are not met, then Vendor is requested to bring submitted work up to acceptance requirements.

8.5 Head Architect can, in consultation with Partners, hold up acceptance of new pull requests from other Vendors, to allow Vendor fix the deficiencies found in submitted work.

8.6 When the changeset meets the acceptance criteria and all the reviewers have accepted the work, then Head Architect pulls in and merges the work into X-Road-tests/develop.

## 9 Bug fixes

When an error is detected, the Partner who located the error is responsible of detecting the source of the error. Detecting the source of the error means tracking the first version of the software that contains the error. When the source is detected the Partner who created the version in question must be notified. The Partner who created the version is responsible of fixing the problem.
