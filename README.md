Employee Leave -- Leave Request ERD
1. Problem Statement
Design a professional, realistic, colorful, and database-standard Entity Relationship Diagram (ERD) for an Employee Leave -- Leave Request system.
Feature Set IV
Employee Details
Department
Leave Request
Leave Dates
Leave History
Approval Status
2. Entities and Attributes
EMPLOYEE
Attribute        Key
Employee_ID      PK Employee_Name
Email
Contact_Number
Department_ID    FK
DEPARTMENT
Attribute         Key
Department_ID     PK Department_Name
LEAVE_REQUEST
Attribute            Key
Leave_Request_ID     PK Employee_ID          FK Leave_Type
Leave_Reason
Start_Date
End_Date
Approval_Status_ID   FK
LEAVE_HISTORY
Attribute            Key
History_ID           PK Employee_ID          FK Leave_Request_ID     FK Start_Date
End_Date
Leave_Type
Approval_Status_ID   FK
APPROVAL_STATUS
Attribute            Key
Approval_Status_ID   PK Status_Name
Status_Date
Approved_By
3. Relationships and Cardinality
Parent Entity     Child Entity      Relationship      Cardinality
DEPARTMENT        EMPLOYEE          A department has  1 : M many employees;
each employee
belongs to one
department
EMPLOYEE          LEAVE_REQUEST     An employee can   1 : M submit many leave requests; each
request belongs
to one employee
EMPLOYEE          LEAVE_HISTORY     An employee can   1 : M have many leave
history records;
each record
belongs to one
employee
LEAVE_REQUEST     LEAVE_HISTORY     A leave request   1 : 1* can have a
corresponding
leave history
record; each
history record
refers to a leave request
APPROVAL_STATUS   LEAVE_REQUEST     One approval      1 : M status can be
associated with
many leave
requests; each
request has one
approval status
APPROVAL_STATUS   LEAVE_HISTORY     One approval      1 : M status can be
associated with
many leave
history records;
each history
record has one
approval status
Note: The Leave Request → Leave History relationship is described as a corresponding record in the problem statement. If the implementation permits multiple history records for one request, model it as 1 : M instead. The ERD should use the cardinality selected by the database requirements.
4. ERD Modeling Rules Used
Rectangles represent entities.
PK identifies the Primary Key of an entity.
FK identifies a Foreign Key that references another entity.
Attributes are grouped within each entity.
Relationship connectors show how entities are associated.
Cardinality is displayed next to relationship connectors.
Foreign keys correspond to the primary keys of referenced entities.
The design follows standard relational database ER modeling conventions.
5. Foreign-Key References
Foreign Key                         References
EMPLOYEE.Department_ID              DEPARTMENT.Department_ID
LEAVE_REQUEST.Employee_ID           EMPLOYEE.Employee_ID
LEAVE_REQUEST.Approval_Status_ID    APPROVAL_STATUS.Approval_Status_ID
LEAVE_HISTORY.Employee_ID           EMPLOYEE.Employee_ID
LEAVE_HISTORY.Leave_Request_ID      LEAVE_REQUEST.Leave_Request_ID
LEAVE_HISTORY.Approval_Status_ID    APPROVAL_STATUS.Approval_Status_ID
6. ERD Structure
The main flow of the database is:
DEPARTMENT → EMPLOYEE → LEAVE_REQUEST → LEAVE_HISTORY
with APPROVAL_STATUS connected to both LEAVE_REQUEST and LEAVE_HISTORY.
This structure supports employee information, departmental organization, leave applications, leave history, and approval tracking.
7. Suggested Visual Design
For a professional and colorful ERD:
Use a distinct color for each entity header.
Keep entity names clearly visible.
Place PK/FK labels directly beside the relevant attributes.
Use straight, clearly routed connectors where possible.
Display cardinality (1, M) beside each connector.
Keep the layout uncluttered and readable.
Use consistent typography and spacing throughout the diagram.
8. Entity Summary
Entity            Purpose
EMPLOYEE          Stores employee details and department assignment DEPARTMENT        Stores department information LEAVE_REQUEST     Stores leave applications submitted by employees LEAVE_HISTORY     Stores historical leave records APPROVAL_STATUS   Stores leave approval/status information
9. Conclusion
The ERD provides a structured database model for an Employee Leave -- Leave Request system. It connects employees with departments, leave requests, leave history, and approval statuses while explicitly identifying primary keys, foreign keys, relationships, and cardinalities.
