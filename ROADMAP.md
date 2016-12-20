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
| Security server performance improvements | Agreed | Improving the scale-up performance of security server, e.g. signer scalability, caching.  | FI/pkivimäki |  FI | 2016
| Central Server notifications | Proposed | The X-Road center needs to receive notifications from the central server when a new request that must be approved is received.  | FI/pkivimäki | ? | 2017
| Security server performance improvements 2 | Agreed | Improving the scale-out performance of security server, e.g. support for external load balancers.  | FI/pkivimäki | FI | 2017
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
| Read only user support | Specified | Read only user support for Security Server UI. This user cannot necessarily see all the settings and is not be able to change anything | FI/hanhaka | FI | 2017
| Ubuntu 16.06 LTS support | Proposed | Support for Ubuntu 16.06 LTS (both Security Server and Central Server). | FI/hanhaka | FI | 2017
| REST Gateway support and packaging | Proposed | REST Gateway DEB and RPM packages as a part of X-Road | FI/hanhaka | FI | 2017
| Federation | Specified | Federation support between Suomi.fi-palveluväylä (Finland) and XTee (Estonia) | FI/hanhaka | FI, EE | 2017
| Messagelog database performance boost | Agreed | Messagelog database performance analysis and improvements to boost database related transactions and functionalities. | FI/hanhaka | FI | 2017
| Messagelog analysis tool | Proposed | Possibility to fetch all organisation specific messages to a file from Messagelog database by using command line tool. | FI/hanhaka | FI | 2017
| Internal load balancing enhancement | Agreed | 'Fastest wins' load balancing principle is improved so that the connection to a service in the subsystem will be established faster. | FI/hanhaka | FI | 2017
| Software update available notification | Proposed | If new software update is available, Security Server UI shows notification on top banner. | FI/hanhaka | FI | 2017
| Environment monitoring data harvesting | Proposed | Environment monitoring harvester collector module is implemented and taken into production. | FI/hanhaka | FI | 2017
| Code quality improvements (exceptions) | Proposed | Generic exceptions should be designed and implemented so that they are application specific exceptions not just using default & generic exception model. | FI/hanhaka | ? | 2017
| Improving the transfer of big attachment files via X-Road | Proposed | Boosting performance of big file transfer via X-Road. | FI/hanhaka | FI | 2017
| Security Server Installation training | Proposed | Hands-on Security Server installation workshop for Finnish organizations. End of Q1. | FI/hanhaka | FI | 2017