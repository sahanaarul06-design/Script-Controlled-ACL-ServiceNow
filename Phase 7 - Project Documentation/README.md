# Phase 7 - Project Documentation

## Project Title

Script-Controlled ACL – Restrict Record Access Based on Field Value

## Documentation Overview

This phase documents the complete ServiceNow project, including the project objective, user and role configuration, table design, ACL configuration, implementation steps, testing process, and results.

The documentation is organized according to the project phases so that the complete development process can be understood clearly.

## Project Objective

The objective of the project is to implement record-level security in ServiceNow using Script-Controlled Access Control Lists.

The project demonstrates how user roles and the Branch field can be used to control access to Institution Details records.

Administrators retain full access to the records.

## User Details

The test user created for the project is:

* User ID: EEE User
* First Name: EEE
* Last Name: User
* Email: [eeeuser@gmail.com](mailto:eeeuser@gmail.com)

## Roles Used

The following roles are used in the ACL implementation:

* bb1 – Read
* bb2 – Create
* bb3 – Write
* bb4 – Delete

## Table Details

The custom table used in the project is:

* Label: Institution Details
* Name: u_institution_details
* Extends for: False

## Fields

The Institution Details table contains:

* Student Roll Number – Auto Number
* Student Name – Reference - User
* Faculty Name – Reference - User
* Branch – Choice
* Email – String
* Phone Number – String
* Description – Multi String

## Branch Choices

The Branch field contains:

* ECE
* EEE
* CSE

## ACL Documentation

### Read ACL

The Read ACL is configured for the Institution Details table.

* Operation: Read
* Required role: bb1
* Data condition: Branch is EEE
* Advanced: Enabled

The script checks for administrator access and the required bb1 role.

### Create ACL

The Create ACL is configured with:

* Operation: Create
* Required role: bb2
* Data condition: None

### Write ACL

The Write ACL is configured with:

* Operation: Write
* Required role: bb3
* Data condition: None

### Delete ACL

The Delete ACL is configured with:

* Operation: Delete
* Required role: bb4
* Data condition: None

## Implementation Documentation

The implementation includes:

1. Creating the test user.
2. Creating the required roles.
3. Assigning roles to the test user.
4. Creating the Institution Details table.
5. Creating the required fields.
6. Adding ECE, EEE, and CSE branch choices.
7. Creating sample records.
8. Elevating security_admin.
9. Creating the Read ACL.
10. Creating the Create ACL.
11. Creating the Write ACL.
12. Creating the Delete ACL.

## Testing Documentation

The project is tested using different users and roles.

Testing includes:

* EEE User access
* User without the required role
* Administrator access
* Read access
* Create access
* Write access
* Delete access

The testing results are recorded using screenshots.

## Screenshot Documentation

Screenshots should be added to the project documentation to provide evidence of the implementation and testing process.

Recommended screenshots include:

* User creation
* Role creation
* Table creation
* Field configuration
* Sample records
* Read ACL configuration
* Read ACL script
* Create ACL
* Write ACL
* Delete ACL
* EEE User impersonation
* Administrator access
* Create operation
* Write operation
* Delete operation

## Phase-wise Documentation

The GitHub repository contains separate folders for the project phases:

* Phase 1 – Brainstorming & Ideation
* Phase 2 – Requirement Analysis
* Phase 3 – Project Design
* Phase 4 – Project Planning
* Phase 5 – Project Development
* Phase 6 – Project Testing
* Phase 7 – Project Documentation
* Phase 8 – Project Demonstration

## Final Documentation

The final documentation brings together the project requirements, design, development, testing, and demonstration details.

The documentation provides a clear record of how Script-Controlled ACLs were implemented to restrict access to records based on roles and field values.

## Project Outcome

The completed project demonstrates the use of ServiceNow ACLs for record-level security and separate control of Read, Create, Write, and Delete operations.

The project documentation serves as a reference for understanding the complete implementation and testing process.
