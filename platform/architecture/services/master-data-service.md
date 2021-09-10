# Master Data Service

Master data service provides interface for maintenance of iFIX master data registries e.g. Government, Chart of Account, Department, Expenditure and Project. 

## Government 

This maintains the Government details and support create and search Government details. While creating the Government , we need a unique Id for the Government and a name for the same. Optionally, we can pass some additional details as part of attribute. In case of search, passing the unique id\(s\) as search parameters can given you all the details of the Government.

## Chart Of Account 

This maintains the Chart of Account\(COA\) details and support create and search COA. While creating the Chart of account, we need to pass the Government Id, majorHead, subMajorHead, minorHead, subHead, groupHead, objectHead and corresponding head names & types. A unique code named COACode will be generated always by combining \(concatenating\) majorHead, subMajorHead, minorHead, subHead, groupHead, objectHead with hyphen\("-"\) and store with the given request.  
Searching the details for COA will be done based on the provided search parameters like chart of account Ids, COACode, Government Id, majorHead, subMajorHead, minorHead, subHead, groupHead, objectHead.

## Department 

Maintains the create and search department details. While creating the department, pass the Government Id, department code, department name, parent department if any. Searching the department details will be on given parameters like ids, Government Id, department code, department name.

## Expenditure 

Maintains the expenditure details And provide create and search functionality. In case of creating the expenditure, need to pass the Government id, department id, code, name , type \(can be "SCHEME","NON\_SCHEME"\) details. While searching the expenditure details, pass the given parameters like ids, Government id, name, code.

## Project 

Maintains the project details and provide create and search functionality. In case of creating the project, need to pass Government, name, code, expenditure id, department entity id, location ids. While searching, pass the ids, Government id, name, code, expenditure id, location id.

![](../../../.gitbook/assets/image%20%2814%29.png)

References

1. [Swagger YAML ](https://redocly.github.io/redoc/?url=https://raw.githubusercontent.com/egovernments/iFix-Dev/develop/domain-services/ifix-master-data-service/ifix-master-data-service-0.1.0.yaml#tag/COA/paths/~1chartOfAccount~1v1~1_search/post)



