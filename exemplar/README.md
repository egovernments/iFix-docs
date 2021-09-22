# Exemplar

To demonstrate the potential of iFIX, an exemplar is being developed in collaboration with the Punjab State Government - Department of Water Supply and Sanitation \(DWSS\). 

DWSS has developed more than 8500 water projects across Punjab. After the construction of these projects, the operations and maintenance of these are done by the GPWSC \(Gram Panchayat Water Scheme Committee\) consisting of members from the local bodies. For the projects that are handed over, GPWSCs is responsible for setting up the water charges, collecting the water charges from the households and manage the expenditure \(O&M\) for the project. 

Due to various reasons, if a GPWSC is unable to fiscally manage the project - the asset deteriorates, water supply to the household is adversely impacted and vendors are unpaid - arrears pile up. For example, the electricity bill which is 75% of the O&M expenses is unpaid. Eventually, these arrears are presented to the State Finance Department for clearance. 

To enable real-time, fiscal visibility of these projects, the following solution was proposed.  The solution consists of 4 components 

1. [mGramSeva ](mgramseva/)- A mobile-based application that will enable GPWSC members and collection agents to collect & manage revenue and expenditure.
2. [iFIX Adapter](ifix-adapter/) - Transforms the Demand, Receipt, Bill and Payment information entered in mGramSeva into anonymized and standardized fiscal events. These are then posted into the iFIX Platform.
3. [iFIX Platform](../) - stores micro-level fiscal data and provides secure standard APIs for source systems to post and query fiscal data in raw and aggregated form.
4. [iFIX Dashboard](ifix-dashboard/) - provides a dashboard for the department to have a real-time view of the fiscal sustainability of various projects.

![](../.gitbook/assets/image%20%2825%29.png)

The project is currently in the last stages of development. Deployment and rollout are expected to commence shortly. 

