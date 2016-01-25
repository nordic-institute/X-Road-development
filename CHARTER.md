# X-Road Joint Development Charter

#### VERSION CONTROL
| version no.	 | what has been done	| date/person
| ---- | ---- | ---- | 
| 0.1	| Initial draft.	| 20.4.15 / PK
| 0.2	| Updated according to comments received in EE-FI telco on 27.4.2015	| 4.5.15 / PK
| 0.9	| Approved for piloting in Steering Committee meeting on 8.6.2015	| 13.6.15 / PK
| 0.91	| Updated according to comments received in EE-FI F2F meeting on 7.7.2015 in Helsinki	| 9.7.15 / PK
| 0.92	| Updated version numbering and SC tasks	| 6.10.15 / OK
| 0.93	| Changed document name to Charter, removed details described in the Workflow document, refences section added	|  22.12.15 / PK
| 0.94  | Conversion to Markdown, moved to xroad-joint-development repo | 25.01.16 / PP

The purpose of this document is to describe the change management process of the X-Road software. The process
must ensure the quality of the source code, the application of best practices and the ability to manage software
changes to be applied to local production environments. The process is controlled by the Steering Committee. 

Non-Functional Requirements are described in the “X-Road Non-Functional Requirements” [X-Road Non-Functional Requirements] document. The workflow policy based on this document is described in the “Workflow Policy [Workflow Policy] document.

## 1 Roles and Responsibilities
The change management process includes the following roles and responsibilities:
*	Steering Committee
  - Accepts / rejects enhancement proposals
  -	Maintains business roadmap
  -	Schedules releases
  -	Nominates the Head Architect for one year at a time
  -	Agrees how security issues are fixed and who produces the fix
*	Head Architect
  -	Supports the Steering Committee on decision making
  -	Maintains technical roadmap
  -	Maintains the master repository
  -	Reviews and accepts / rejects contributions
*	Partner
  -	Nominates representatives to the Steering Committee
  -	Submits enhancement proposals
  -	Submits code contributions including required documentation 
  -	Produces bug fixes and security bug fixes

## 2 Roadmap Management
A roadmap is a plan that outlines the flow of new features needed to satisfy the needs of X-Road partners.
The roadmap helps reach a consensus about future developments and it provides a framework to help plan and
coordinate upcoming releases. The X-Road roadmap takes into consideration scoped functionality and X-Road
production compatibility. 
 
Diagram 1. Business roadmap management.

The roadmap is divided in two parts: business roadmap and technical roadmap. The business roadmap is owned
and managed by the Steering Committee and is updated through the scoping process. All the changes to the X-Road
Roadmap must go through the standard approval process through the Steering Committee and scheduled for a release,
regardless of issue type (core, extension). The technical roadmap is managed by the head architect, and
it contains fine grained technical items derived from the business roadmap items.  
 
Diagram 2. Technical roadmap management.

### 2.1 Scoping Process
The determination of what development is in scope of a X-Road Release is determined by the Steering Committee
through a scoping process (diagram 1). Inputs to this process are provided by X-Road development partners.

##### 2.1.1 Core System
All the changes to the X-Road core must be approved by the Steering Committee. Adding a new core item to the roadmap
is done by submitting a formal enhancement proposal that includes functional and technical description of the item.
The technical description must contain a description of the architectural changes required by the item and a plan
for the implementation. The Steering Committee accepts or rejects the proposal. Accepted proposals are added to
the roadmap. Rejected proposals can be resubmitted after modification.

Alternatively, a new enhancement proposal can be submitted without the technical de-scription, and get accepted
to the roadmap. However, the technical description must be submitted, and accepted by the Steering Committee prior to the implementation.

##### 2.1.2 Extensions
All the extensions must be notified to the Steering Committee by submitting a formal ex-tension notice. The notice
must include a functional description of the extension. Adding a technical description of the extension to notice is highly recommended, but not mandatory. The Steering Committee adds the extension to the roadmap.

### 2.2 Security Bug Fixes
All issues on critical updates shall be brought to the Steering Committee. The Steering Committee agrees how the 
security issue is fixed and which partner produces the patch.

## 3 Warranty
When an error is detected, the Partner who located the error is responsible of detecting the source of the error. Detecting the source of the error means tracking the first version of the software that contains the error. When the source is detected the Partner who created the version in question must be notified. The Partner who created the version is responsible of fixing the problem.

## 4 Release Sequence
The determination of what sequence a release will be identified with will be determined by the X-Road Steering Committee.
A basic software rule of thumb will be as follows.
*	Major Release (X.0) will be used for significant jumps in functionality such as changing the framework which could
cause incompatibility with interfacing systems or new modules/components.
*	Minor Release (X.X) will be used when only minor features or significant fixes have been added.
*	Revision Release (X.X.X) is used and incremented when minor bugs are fixed.

At times the release sequence may jump multiple minor versions at a time to indicate sig-nificant features have been
added, but are not enough to warrant incrementing a major version number. 
See Non Functional Requirements [X-Road Non-Functional Requirements] document for more detailed information on version
numbering.

## 5 Version Compatibility
Major versions of X-Road are intended to be longlived versions of the software which consist of numerous minor versions.
The decision to create a new major version of X-Road will be the result of the need for major changes which cannot be
successfully implemented without breaking version compatibility.

#### References
- [X-Road Non-Functional Requirements] X-Road Non-Functional Requirements.
- [Workflow Policy] Workflow Policy, https://github.com/e-gov/Open-Workflow/blob/master/WORKFLOW.md. 
