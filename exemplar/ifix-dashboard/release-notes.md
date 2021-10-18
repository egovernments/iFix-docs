---
description: Reference Dashboard Release Details
---

# Release Notes

## Release Summary

Metabase, an open-source business intelligence platform is being used for visualising the reference dashboard of iFIX.

Financial transactions are done on mGramSeva such as demand generation, receipt collection, the addition of bill and payment records come into Metabase through iFIX in the form of Fiscal events.

These Fiscal event line items are aggregated to form various data points that provide insights to department officials on Reference Dashboard(Metabase)

## Release Description

Here, we’ll see how different options on Metabase works.

![](<../../.gitbook/assets/image (59).png>)



## Filters on the Dashboard

### **Date/Time Filter**

The date & time filter on the dashboard defaults to the **current financial** year since most of the calculations and visualisations makes sense when viewed from a fiscal year perspective rather than an individual week/month view. However, users can change to respective dates and most charts will be filtered to the selected time range.

### **Department Hierarchy Filter**

Currently, there are 6 levels of hierarchy as per administration set up by the Department of Water supply and Sanitation Punjab. These are State, Zone, Circle, Division, Sub Division, Section, Gram Panchayat.&#x20;

All these filters are independent and work on the dashboard irrespective of whether other filters in the hierarchy are selected or not.

### Visualisations/ Metrics on Dashboard

#### Surplus/Deficit <a href="surplus-deficit" id="surplus-deficit"></a>

This number shows whether the selected Administrative entity is financially surplus or not. It also compares with the previous year using the “trend” visualisation in Metabase.&#x20;

**Pending Collections**

For selected Administrative boundary what is the pending collections through water charges is represented in this card. If the pending amount is null. Then this card should display zero.&#x20;

**Outstanding Electricity Bills**

Since electricity bills create a major component of the expenditure for all projects, it is important to show how much electricity bills are pending at each administrative entity. The total amount of pending bills filtered by electricity under COA gives us pending electricity bills

**GPWSCs at Risk**

Risky GPWSCs are divided into 3 types

* High risk: Demand is less than Bill.
* Medium Risk: Demand is more than bill but pending collections are less than pending bills.
* Low Risk: Demand is more than bill and also pending collections is more than pending bills.

It is important to identify the risky GPWSCs and keep the officials of DWSS informed, for them to take the right actions before it’s too late.

**Collections & Expenditure time series graphs**

These charts represent the Demand, Net Collections, Bills and Net Payments across time(month-on-month) so that officials get a fair idea of how the amount that is getting collected is being spent.&#x20;

Any abnormalities in the graphs (Low collections or excessive spending) is something that needs to be paid attention to.&#x20;

**Expenditure by Chart of Accounts**

Expenditure is currently divided into 4 broad categories - Electricity Bills, Salaries, Operations and Maintenance and Miscellaneous. How these 4 categories accumulate to total expenditure for the selected entity over time is presented on the chart. Usually, 75% of the expenditure should be of type electricity

**Department hierarchy table**

Here, we represent Total Demand, Receipt, Bills and Payments by all levels of the hierarchy so that officials at any point, instead of just viewing the charts, trends from the visualisations can also see the tables and compare best performing entities. \
