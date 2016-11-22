# Backlog of Joint X-Road Development

## About

Backlog is a list of technical 'features' that are or will be developed to X-Road core technology.
Current document describes how backlog items are to be handled.

## Process

* Backlog items are [issues](https://github.com/vrk-kpa/xroad-joint-development/issues) in the [xroad-joint-development repository](https://github.com/vrk-kpa/xroad-joint-development).
* Items are named as user stories ("who", "where" and "what"). Bugs are named as 'BUG: "where" and "what"'. 
* New functionality is labeled as ["enhancement"](https://github.com/vrk-kpa/xroad-joint-development/labels/enhancement).
* Issues that are fixes for existing functionality are labeled as ["bug"](https://github.com/vrk-kpa/xroad-joint-development/labels/bug).
* Issues must have up to 1 label defining its status in the backlog: (no status label)/"pending", "assigned", "wip" (work-in-progress), "done", "wontfix". 
* Before initiating development activities the item must be described in backlog and achieve "assigned" or "wip" status from the workgroup.
  * Contributions from public domain are also handled following the same scheme - i.e. public domain contribution is not automatically accepted but rather sufficient understanding is built on the change and best time to merge it is scheduled in relation to other backlog items.
  * Critical patches can be made by adding an issue to the backlog, informing the workgroup and adding relevant information (see "assigned" status below) ASAP. Label "bug" is used to emphasize the type.
* Issues are additionally labeled by decision of the workgroup as follows:
  * (no label)/"pending" - proposed items that need discussion and decision in the workgroup. If common understanding is not met within several workgroup meetings the item is closed with label "wontfix".
  * "assigned" - sufficiently described items that has an owner who will solve it. An "assigned" backlog item ("enhancement" or "bug") will have the following contents described:
    * Assignee is assigned (Head Architect for Public Domain assignments). 
    * Priority / Estimated development time
    * Rough estimated list of core components that are to be modified or created (follow the component architecture described in the architecture documents)
    * Rough estimation of documentation that is to be modified or created (follow the documentation masterlist found at ...)
    * The issue should have a [milestone](https://github.com/vrk-kpa/xroad-joint-development/milestones) indicating the rough schedule estimate when the issue is going to be resolved
  * "wip" - backlog item, that is being worked on. Must have an estimated delivery [milestone](https://github.com/vrk-kpa/xroad-joint-development/milestones). Must contain the following piece of information: the contact person who is dealing with the item. All other contributors are considered to be aware of the fact that mentioned components and documentation is changed and during this phase.
    * Keeping up to date the affected components and documentation list.  
* Backlog items that are resolved will be "closed" and a status is assigned:
  * "wontfix" - backlog items that are analyzed and found to be unneccessary and will not be fix nor new functionality added.
  * "done" - items that are merged to main development branch (see workflow for more details on branches). 
    * Added reference to commit.
    * The commit must have a reference to the backlog.
* Relevant information is kept in the backlog issue description.
