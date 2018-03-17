This Roadmap is out-of-date and it is no longer maintained. New Roadmap will be published by the [Nordic Institute for Interoperability Solutions (NIIS)](https://niis.org) during spring 2018.

# Abstract

Current document postulates the major changes that are identified and about for further analysis and planning.

* Label - short name for the item
* Status - possible statuses are.
   * agreed - agreed and sufficiently specified.
   * specified - general agreement exists. Needs further specification.
   * proposed - proposal to be discussed in workgroup and steering.
   * postponed - priority shall be made decided in a later time.
   * delegated - third party that takes responsibility for dealing with this.
* Description - short description of the issue
* Reporter - who submitted the item
* Responsible - who delivers the item
* Priority - expected order of delivery.

# RoadMap

| Label | Status | Description | Reporter | Responsible | Priority
| ----| ---- | ---- | ---- | ---- | ----
| Service monitoring | Done  | Member needs availability statistics and characteristics for processed messages. Center collects service statstics from members.  | EE/hvainsalu | RIA/tmolder | 2016
| Federation | Agreed | Federation support between Suomi.fi-palveluväylä (Finland) and X-tee (Estonia) | FI/hanhaka | FI, EE | Q1 2017
| X-Road protocol stack standard | Specified | For transparency X-Road ecosystem governance needs X-Road Protocol to be clearly defined (incl BackLog #31). | EE/hvainsalu | RIA/ott-vitali | 2017 
| NFR security ammendments | Specified | Add additional security related requirement to NFR for core developers | EE/hvainsalu | EE/vstupin | Q2 2017
| Message processing improvements | Specified | Backlog #33, #55, #71 | EE/hvainsalu | EE/pelm | Q2 2017
| Improve management in central server | Specified | #117, #124 | EE/hvainsalu | EE/pelm | Q2 2017
| Compliance to NFR | Specified | Solve backlog items #39, #41, #43 + output of security testing | EE/hvainsalu | EE/pelm | Q4 2017
| Service Developer Trainings | Specified | Public Estonian and English materials for service developer class trainings | EE/hvainsalu | EE/pelm | Q3 2017
| Security Server operational and maintenance training | Agreed | Hands-on Security Server operational and maintenance workshop for Finnish organizations | FI/hanhaka | FI | Q2 2017
| Centralized log management | Proposed | Centralized log management system where all the environmental and service monitoring information is stored. Includes the component that harvests the logs from secyrity servers. | FI/pkivimäki | FI/? | 2016
| Security server performance improvements | Agreed | Improving the scale-up performance of security server, e.g. signer scalability, caching.  | FI/pkivimäki |  FI | 2016
| Central Server notifications | Proposed | The X-Road center needs to receive notifications from the central server when a new request that must be approved is received.  | FI/pkivimäki | ? | 2017
| Security server performance improvements 2 | Agreed | Improving the scale-out performance of security server, e.g. support for external load balancers.  | FI/pkivimäki | FI | 2017
| REST support | Specified | REST Gateway extension that provides automated SOAP-REST conversion. The configuration of the extension can be done through security server UI. | FI/pkivimäki/hanhaka | FI | Q3 2017
| Security server clustering | Proposed | When the same service is published on multiple security servers, the service configuration must be replicated to all the instances, e.g. when access rights are updated, the change must automatically be replicated to all the instances of the service. | FI/pkivimäki | ? | 2017
| RHEL support for central server | Postponed | It must be possible to run central server on RHEL platform. | FI/pkivimäki | NIIS? | 2018
| Ubuntu 18.04 LTS support | Specified | Support for Ubuntu 18.04 LTS (both Security Server and Central Server). | FI/hanhaka | NIIS? | 2018
| Read only user support | Agreed | Read only user support for Security Server UI. This user cannot necessarily see all the settings and is not be able to change anything | FI/hanhaka | FI | Q2 2017
| REST Gateway support and packaging | Specified | REST Gateway DEB and RPM packages as a part of X-Road | FI/hanhaka | FI | Q2 2017
| Messagelog database performance boost | Agreed | Messagelog database performance analysis and improvements to boost database related transactions and functionalities. | FI/hanhaka | FI | Q2 2017
| Messagelog analysis tool | Specified | Possibility to fetch all organisation specific messages to a file from Messagelog database by using command line tool or some other tool. | FI/hanhaka | FI | H2 2017
| Internal load balancing enhancement | Agreed | 'Fastest wins' load balancing principle is improved so that the connection to a service in the subsystem will be established faster. | FI/hanhaka | FI | H2 2017
| Software update available notification | Specified | Automatic mechanism to notify on UI when new software update is available. | FI/hanhaka | FI | H2 2017
| Environment monitoring data harvesting | Agreed | Environment monitoring harvester collector module is implemented and taken into production. | FI/hanhaka | FI | Q2 2017
| Code quality improvements (exceptions) | Agreed | Generic exceptions should be designed and implemented so that they are application specific exceptions not just using default & generic exception model. | FI/hanhaka | FI & EE | Q3 2017
| Improving the transfer of big attachment files via X-Road | Specified | Boosting performance of big file transfer via X-Road. | FI/hanhaka | FI | H2 2017
| X-Road approach to eDelivery | Proposed | Find unified approach how an X-Road ecosystem relates to eDelivery platform (translation, security etc | EE/hvainsalu | ? | A
| Reusage of existing certificates for member | Proposed | Member must be able to use security tokens on a signing device that are complient to X-Road requirement | EE/vainsalu | ? | A
| Member management management services | Proposed | Members need that memeber management tasks are efficient and troubleless. Management services that would support usage of external case systems for convenient membership and seamless access controll of services. | EE/hvainsalu | ? | ?
| Service deployment with quelity assurance | Proposed | Center needs all deployed services to be compliant and well described | EE/hvainsalu | ? | B
| Global Group API | Proposed | Members need to allow service usage to certain set of members - jet they do not govern this set by themselves nor does X-Road center. | EE/hvainsalu | ? | B
| X-Road debug utils | Proposed | Members need support when debuging technological issues with X-Road components | EE/hvainsalu | ? | C
| Security categories | Postponed | Members need to be aware of security conformance of other members | EE/hvainsalu | ? | X
| KSI technology timestamp support | Delegated | Member needs cost effective timestamping | EE/hvainsalu | GuardTime | X | X
