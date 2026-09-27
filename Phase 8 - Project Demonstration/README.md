# Phase 8 – Project Demonstration

## 1. Project Introduction

The project demonstrates how Script-Controlled Access Control Lists (ACLs) can be used in ServiceNow to restrict access to records based on user roles and field values.

## 2. User and Role Demonstration

The EEE User is created and the required roles are assigned:

* bb1 – Read access
* bb2 – Create access
* bb3 – Write access
* bb4 – Delete access

## 3. Table Demonstration

The custom table `u_institution_details` is demonstrated with the following fields:

* Student Roll Number
* Student Name
* Faculty Name
* Branch
* Email
* Phone Number
* Description

The Branch field contains ECE, EEE and CSE choices.

## 4. Record Demonstration

Sample records are created with different branch values such as:

* ECE
* EEE
* CSE

## 5. Read ACL Demonstration

The Read ACL is configured with the Branch condition as EEE and the required script-controlled access.

The EEE user can view the allowed EEE records, while the administrator retains full access.

## 6. Create ACL Demonstration

A Create ACL is configured with the `bb2` role.

Users having the required role can create records according to the project access configuration.

## 7. Write ACL Demonstration

A Write ACL is configured with the `bb3` role.

Users having the required role can edit records according to the project access configuration.

## 8. Delete ACL Demonstration

A Delete ACL is configured with the `bb4` role.

Users having the required role can delete records according to the project access configuration.

## 9. Testing Demonstration

The project is demonstrated by impersonating different users and checking their access to the Student Records list.

The following are demonstrated:

* EEE User access
* User without the required role
* Administrator full access
* Create operation
* Write operation
* Delete operation

## 10. Screenshot Evidence

Screenshots are included as evidence of the project implementation and testing.

## 11. Final Outcome

The demonstration shows how ServiceNow ACLs and scripts can be used to provide record-level security and restrict unauthorized access.
