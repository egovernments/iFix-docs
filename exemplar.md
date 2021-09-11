# Exemplar

To demonstrate the potential of iFIX, an exemplar is being developed in collaboration with the Punjab State Government - Department of Water Supply and Sanitation \(DWSS\). 

DWSS has developed more that 8500 water projects across Punjab. After construction of these projects, the operations and maintenance of these are done by the GPWSC \(Gram Panchayat Water Scheme Committee\) consisting of members from the local bodies. For the projects that are handed over, GPWSCs is responsible for setting up the water charges, collecting the water charges from the households and manage the expenditure \(O&M\) for the project. 

Due to various reasons, if a GPWSC is unable to fiscally manage the project - the asset deteriorates, water supply to household is adversely impacted and vendors are unpaid - arrears pile up. For example, the electricity bill which is 75% of the O&M expenses is unpaid. Eventually these arrears are presented to the State Finance Department for clearance. 

To enable real time, fiscal visibility of these projects, the following solution was proposed.  The solution consists of 4 components 

1. [mGramSeva ](related/mgramseva/)- A mobile based application that will enable GPWSC members and collection agents to collect & manage revenue and expenditure.
2. [iFIX Adapter](related/ifix-adapter.md) - Transforms the Demand, Receipt, Bill and Payment information entered in mGramSeva into anonymized and standardized fiscal event. These are then posted into iFIX Platform.
3. [iFIX Platform](./) - stores micro level fiscal data and provides secure standard APIs for source systems to post and query fiscal data in raw and aggregate form.
4. [iFIX Dashboard](related/ifix-dashboard/) - provides a dashboard for department to have real time view the fiscal sustainability of various projects.

![](.gitbook/assets/image%20%2824%29.png)

The project is current in the last stages of development. Deployment and roll out is expected to commence shortly. 

