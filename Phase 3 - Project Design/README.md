# Phase 3 - Project Design

## Project Title

Script-Controlled ACL – Restrict Record Access Based on Field Value

## Design Overview

The project is designed to implement record-level security in ServiceNow using Access Control Lists (ACLs), user roles, field values, and an advanced script.

The main design is based on controlling access to the Institution Details table according to the Branch field and the roles assigned to users.

## User and Role Design

A test user named EEE User is created for testing the ACL configuration.

The following roles are designed for different operations:

* bb1 – Read
* bb2 – Create
* bb3 – Write
* bb4 – Delete

These roles are used to test different levels of access.

## Table Design

The custom table is designed as:

**Label:** Institution Details

**Name:** u_institution_details

**Extends for:** False

The table stores student-related information and includes a Branch field that is used for access control.

## Field Design

The table contains the following fields:

| Field               | Type             |
| ------------------- | ---------------- |
| Student Roll Number | Auto Number      |
| Student Name        | Reference - User |
| Faculty Name        | Reference - User |
| Branch              | Choice           |
| Email               | String           |
| Phone Number        | String           |
| Description         | Multi String     |

## Branch Field Design

The Branch field contains three choices:

* ECE
* EEE
* CSE

The Branch field is important because the Read ACL uses the EEE branch condition to restrict record access.

## Record Design

Multiple records are created in the Institution Details table.

The records contain different branch values such as:

* ECE
* EEE
* CSE

These records are used to verify whether access restrictions work correctly.

## Read ACL Design

A Record-level Read ACL is designed for the Institution Details table.

Configuration:

* Type: record
* Operation: read
* Name: u_institution_details
* Active: true
* Advanced: true
* Requires role: bb1
* Data condition: Branch is EEE

The advanced script checks the user's role and controls access.

The design also provides full access for administrators.

## Create ACL Design

A Record-level Create ACL is designed for the Institution Details table.

Configuration:

* Type: record
* Operation: create
* Name: u_institution_details
* Active: true
* Requires role: bb2
* No data condition

This ACL controls the ability to create new Institution Details records.

## Write ACL Design

A Record-level Write ACL is designed for the Institution Details table.

Configuration:

* Type: record
* Operation: write
* Name: u_institution_details
* Active: true
* Requires role: bb3
* No data condition

This ACL controls the ability to edit records.

## Delete ACL Design

A Record-level Delete ACL is designed for the Institution Details table.

Configuration:

* Type: record
* Operation: delete
* Name: u_institution_details
* Active: true
* Requires role: bb4
* No data condition

This ACL controls the ability to delete records.

## Administrator Access Design

Administrators are designed to retain full access to the Institution Details records.

The Read ACL script includes an administrator check so that administrators can access the records without the normal branch restriction.

## Security Design

The overall security design separates the four CRUD operations:

* Read → bb1
* Create → bb2
* Write → bb3
* Delete → bb4

This makes it possible to test and demonstrate different permissions independently.

## Testing Design

The project is designed to be tested using ServiceNow impersonation.

The following users and roles are considered during testing:

* EEE User with required roles
* User without the required role
* Administrator

The expected behavior is checked by opening the Institution Details list and attempting the relevant operations.

## Expected Design Outcome

The completed design should demonstrate how ServiceNow ACLs can be used to control record access based on user roles and field values.

It should also demonstrate separate control over Read, Create, Write, and Delete operations while allowing administrators full access.
