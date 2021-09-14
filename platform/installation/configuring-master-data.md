# Configuring Master Data

## **ADMIN ONLY**

Before the iFIX platform can be used, the master data must be configured directly into the respective collections in MongoDB. Associated APIs for configuring Master Data will be made available in the next version. 

1. Add Government - Insert into MongoDB collection
2. Add Department 

   Add Department Hierarchy - It defines the hierarchy definition for the department. 

   1. department id: It is master department id \(UUID\)
   2. level: It defines the depth of hierarchy of department level. 
      1. Root level department hierarchy will not contain any parent value and level value will be zero.
      2. Level value incrementation rule:
         1. When parent id is having any value then we search parent in department hierarchy record for hierarchy level evaluation.
         2. Get level value from parent department hierarchy and increment current department hierarchy level value by one.
   3. parent: It provides details about department parent \(UUID\).

   Add Department Entity - It contains department entity information along with its hierarchy level and also attaches master department information \(department id - UUID\). Here we keep all children information list at every department node \(department record\). Leaf level department will not have any children info. Children list contains department entity id list, which makes current department entity parent of all children list \(department id list\), that's how it maintains department entity level. Entities can be created by 

   1. First defining the hierarchy level top to bottom because it has parent's reference.
   2. Then we can start adding department entities, bottom-to-top because it has child's reference.

   **Note**:

   1. The root department hierarchy will have the label "Department", and the root department entity will be the department itself.\_
   2. When we have to update the existing children list of Department Entity then update the existing children list using mongodb command like below:
      1. Find the department entity parent where the new children need to be added. Do search by name and hierarchy level `db.departmentEntity.find({"name" : "<current_department_entity's_name>","hierarchyLevel": <Current_department_entity_hierarchy_level>});`
      2. Append the department entity id at the end of the current department entity children's list. So first find the length of the current array and then set it as "children.n": "" \(where n is the length of the array.\)`db.departmentEntity.update({"_id": ""},{$set: {"children.n": "", "children.n+1": ""} })`

3. Add Chart of Accounts - Insert manually into MongoDB collection.
4. Add Expenditure - Insert manually into MongoDB collection.

