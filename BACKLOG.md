# Backlog of Joint X-Road Development

## About

Backlog is a list of technical 'features' that are or will be developed to X-Road core technology.
Current document describes how backlog items are to be handled.

## Process

* Backlog items are issues in the xroad-joint-development repository.
* Items are named as user stories ("who", "where" and "what"). Bugs are named as 'BUG: "where" and "what"'. 
* New functionality is labeled as "enhancement".
* Issues that are fixes for existing functionality is labeled as ["bug"](https://github.com/vrk-kpa/xroad-joint-development/labels/bug).
* Issues must have up to 1 label defining its status in the backlog: (no status label)/"pending", "assigned", "wip" (work-in-progress), "done", "wontfix". 
* Before initiating development activities the item must be described in backlog and achieve "assigned" or "wip" status from the workgroup.
  * Contributions from public domain are also handled following the same scheme - i.e. public domain contribution is not automatically accepted but rather sufficient understanding is built on the change and sheduled best time to merge it in the relation to other backlog items.
  * Critical patches can be made whan adding it to backlog, informing the workgroup and adding relevant information (see "assigned" status below) ASAP (Should we also label them? to make understanging of items that have not passed regular workgroup acceptance?). Label "bug" is used to emphasize the type.
* Issues are additionally labeled by decision of the workgroup as follows:
  * (no label)/"pending" - proposed items that need discussion and decision in the workgroup. If common understanding is not met within several work-group meetings the item is closed with label "wontfix".
  * "assigned" - sufficiently described items that has an owener who will solve it. An "assigned" backlog item ("enchanement" or "bug") will have the folowing contents described:
    * Assignee is assigned (Ilka for Public Domain assignments). 
    * Priority / Estimated development time
    * Rough estimated list of core components that are to be modified or created (follow the component architecture described in the architecture documents)
    * Rough estimation of documentation that is to be modified or created (follow the documentation masterlist found at ...)
  * "wip" - backlog item, that is being worked on. Must have an estimate delivery version/milestone. Must contain the following piece of information: the contact person who is dealing with the item. All other contributors are considered to be aware of the fact that mentioned components and documentation is changed and during this phase.
    * Keeping up to date the affected components and documentation list.  
* Backlog items that are resolved will be "closed" and a status is assigned:
  * "wontfix" - backlog items that are analyzed and found to be unneccessary and will not be fix nor new functionality added.
  * "done" - items that are merged to main development branch (see workflow for more details on branches). 
    * Added reference to commit.
    * The commit must have a reference to the backlog.
* Relevant information is kept in the backlog issue description.
