# Phase 2 - Requirement Analysis

## Project Title

Script-Controlled ACL – Restrict Record Access Based on Field Value

## Requirement Overview

The project requires implementing record-level security in ServiceNow using Access Control Lists (ACLs).

The main requirement is to restrict access to Institution Details records based on the Branch field and user roles.

## User Requirement

A test user named EEE User is created for testing the access restrictions.

User details:

* User ID: EEE User
* First Name: EEE
* Last Name: User
* Email: [eeeuser@gmail.com](mailto:eeeuser@gmail.com)

## Role Requirements

Four custom roles are required for controlling different operations:

* bb1 – Read access
* bb2 – Create access
* bb3 – Write access
* bb4 – Delete access

All four roles are assigned to the EEE User for testing the complete ACL functionality.

## Table Requirement

A custom table named Institution Details is required.

Table name:

`u_institution_details`

The table should not extend another table.

## Field Requirements

The Institution Details table requires the following fields:

1. Student Roll Number – Auto Number
2. Student Name – Reference - User
3. Faculty Name – Reference - User
4. Branch – Choice
5. Email – String
6. Phone Number – String
7. Description – Multi String

## Branch Values

The Branch field should contain the following choices:

* ECE
* EEE
* CSE

## Record Requirements

Multiple Institution Details records should be created with different branch values such as ECE, EEE, and CSE.

These records are required to test whether the ACL correctly restricts access according to the Branch field.

## Read Access Requirement

A Read ACL must be created for the Institution Details table.

The Read ACL should:

* Use the record type.
* Use the Read operation.
* Require the bb1 role.
* Use Branch is EEE as the data condition.
* Use an advanced script.
* Allow administrators full access.
* Allow authorized EEE users to view the required records.
* Deny access to unauthorized users.

## Create Access Requirement

A Create ACL must be created for the Institution Details table.

The Create ACL should:

* Use the record type.
* Use the Create operation.
* Require the bb2 role.
* Allow authorized users to create records.

## Write Access Requirement

A Write ACL must be created for the Institution Details table.

The Write ACL should:

* Use the record type.
* Use the Write operation.
* Require the bb3 role.
* Allow authorized users to edit records.

## Delete Access Requirement

A Delete ACL must be created for the Institution Details table.

The Delete ACL should:

* Use the record type.
* Use the Delete operation.
* Require the bb4 role.
* Allow authorized users to delete records.

## Administrator Requirement

Administrators should retain full access to the records.

## Testing Requirements

The project must be tested by impersonating different users and checking the available records and operations.

The testing should verify:

* EEE user access.
* Users without the required role.
* Administrator access.
* Read access.
* Create access.
* Write access.
* Delete access.

## Expected Result

The completed ACL configuration should demonstrate how ServiceNow can use roles, field values, and scripts to control access to records and protect data from unauthorized access.
