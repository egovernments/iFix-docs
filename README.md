---
description: Fiscal Information Exchange Platform
---

# iFIX

## Introduction

iFIX is an information exchange infrastructure \(similar to highways\) that will facilitate the exchange of fiscal information across central, state and local governments and also between various departments in a standardized manner.  It is being developed as an open Public Digital Good \(PDG\) that can be leveraged by any government. 

Fiscal information exchange has followed the conventional route using point to point integration so far.  iFIX enables any existing and future government agency to exchange information with each other through a standard fiscal information exchange bus. 

![Point to Point vs Bus Based Integration](.gitbook/assets/image%20%2845%29.png)

iFIX is designed keeping in view the federal structure of governments. Each government agency can define what it can share with other agencies and iFIX will enable the real-time seamless exchange of this information through standards-based protocols.

![Proposed Federated Architecture of iFIX Platform](.gitbook/assets/image%20%2816%29.png)

Each iFIX instance will itself be multi-tenant and will enable multiple local systems to post standardized and anonymized micro-level fiscal data as **Fiscal Events.** Fiscal Events can be of type - Demand, Receipt, Bill, Payment. In the future, it will also include Budget events e.g. Sanctions, Appropriation, Allocation and Transfers. This will enable IFMS/PFMS systems to communicate seamlessly to downstream systems.

![iFIX Platform Architecture](.gitbook/assets/image%20%2841%29.png)

iFIX facilitates exchange of fiscal information through a standard set of API \(Application Program Interfaces\)  and events that are available in the [Standards](platform/standards/) section.

iFIX provides standard APIs for management of master data like Departments, Funds, Charts of Accounts, Expenditures \(e.g. Schemes, Non-Scheme\) and Projects. Client systems can register into iFIX and based on the permissions granted use the APIs to manage the master data and/or post-primary fiscal events e.g. Demand, Receipt, Bill, Payment. FIX then makes this information available through Standard API for aggregated and dis-aggregated forms for other systems to query and leverage.

![Chain of Events](.gitbook/assets/image%20%2854%29.png)

As events flow into iFIX, it will enable real-time correlation of various **chain of events** and be able to provide visibility of fiscal and cash position of various assets, projects and agencies that are critical in delivering reliable services to citizens. 

## Use Cases

iFIX can be used for a variety of use cases 

1. National Governments can use FIX to exchange fiscal information about various national funded programs with state and local governments.
2. State Governments can use FIX to exchange fiscal information about various national funded and state-funded programs across various departments.
3. Local Governments can use FIX to exchange fiscal information with various state and national departments. 

\*\*\*\*

