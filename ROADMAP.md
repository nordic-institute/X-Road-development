Roadmap

# Abstract

Current document postulates the major changes that are identified and about for further analysis and planning.

* Label - short name for the item
* Status - possible statuses are.
   * agreed - agreed and sufficiently specified.
   * proposed - proposal to be discussed in workgroup and steering.
   * specified - general agreement exists. Needs further specification.
* Description - short description of the issue
* Reporter - who submitted the item
* Responsible - who delivers the item
* Priority - expected order of delivery.

# RoadMap

| Label | Status | Description | Reporter | Responsible | Priority
| ----| ---- | ---- | ---- | ---- | ----
| Service monitoring | Agreed  | Member needs availability statistics and characteristics for processed messages. Center collects service statstics from members.  | EE/hvainsalu | RIA/tmolder | 2016
| X-Road protocol stack standard | Specified  | For transparency X-Road ecosystem governance needs X-Road Protocol to be clearly defined. | EE/hvainsalu | RIA/? | 2016 
| Centralized log management | Proposed | Centralized log management system where all the environmental and service monitoring information is stored. Includes the component that harvests the logs from secyrity servers. | FI/pkivimäki | FI/? | 2016
| Security server performance improvements | Proposed | Improving the scale-up performance of security server, e.g. signer scalability, caching.  | FI/pkivimäki |  ? | 2016
| Central Server notifications | Proposed | The X-Road center needs to receive notifications from the central server when a new request that must be approved is received.  | FI/pkivimäki | ? | 2016
| Security server performance improvements 2 | Proposed | Improving the scale-out performance of security server, e.g. support for external load balancers.  | FI/pkivimäki | ? | 2017
| REST support | Proposed | REST Gateway extension that provides automated SOAP-REST conversion. The configuration of the extension can be done through security server UI. | FI/pkivimäki | ? | 2017
| Security server clustering | Proposed | When the same service is published on multiple security servers, the service configuration must be replicated to all the instances, e.g. when access rights are updated, the change must automatically be replicated to all the instances of the service. | FI/pkivimäki | ? | 2017
| RHEL support for central server | Proposed | It must be possible to run central server on RHEL platform. | FI/pkivimäki | FI/? | 2017
| Member management management services | Proposed | Members need that memeber management tasks are efficient and troubleless. Management services that would support usage of external case systems for convenient membership and seamless access controll of services. | EE/hvainsalu | ? | A
| Service deployment with quelity assurance | Proposed | Center needs all deployed services to be compliant and well described | EE/hvainsalu | ? | A
| Security categories | Proposed | Members need to be aware of security conformance of other members | EE/hvainsalu | EE/? | A
| KSI technology timestamp support | Proposed | Member needs cost effective timestamping | EE/hvainsalu | ? | B
| Global Group API | Proposed | Members need to allow service usage to certain set of members - jet they do not govern this set by themselves nor does X-Road center. | EE/hvainsalu | ? | B
| X-Road Center Hi-Av Support | Proposed | Members need central ecosystem availability (nor availability of Trust Federation) not be jeopardized with non-temporary damage to central components. | EE/hvainsalu | ? | C
| X-Road debug utils | Proposed | Members need support when debuging technological issues with X-Road components | EE/hvainsalu | ? | C
| Reusage of existing certificates for member | Proposed | Member must be able to use security tokens on a signing device that are complient to X-Road requirement | EE/vainsalu | ? | A
