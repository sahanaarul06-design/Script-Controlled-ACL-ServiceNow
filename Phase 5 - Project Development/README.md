# Phase 5 - Project Development

## Project Title

Script-Controlled ACL – Restrict Record Access Based on Field Value

## Development Overview

The project is developed in ServiceNow by creating the required user, roles, custom table, fields, sample records, and Access Control Lists.

The development process follows the requirements and design prepared in the previous phases.

## Step 1 – Create Test User

A test user is created with the following details:

* User ID: EEE User
* First Name: EEE
* Last Name: User
* Email: [eeeuser@gmail.com](mailto:eeeuser@gmail.com)

This user is used to test the ACL restrictions.

## Step 2 – Create Roles

The following roles are created:

* bb1
* bb2
* bb3
* bb4

All four roles are assigned to the EEE User for testing the different access operations.

## Step 3 – Create Institution Details Table

A custom table is created with:

* Label: Institution Details
* Name: u_institution_details
* Extends for: False

The table is used to store student and branch information.

## Step 4 – Create Table Fields

The following fields are added:

* Student Roll Number – Auto Number
* Student Name – Reference - User
* Faculty Name – Reference - User
* Branch – Choice
* Email – String
* Phone Number – String
* Description – Multi String

## Step 5 – Configure Branch Choices

The Branch field is configured with these choices:

* ECE
* EEE
* CSE

## Step 6 – Create Sample Records

Multiple records are created in the Institution Details table.

The records contain different Branch values such as ECE, EEE, and CSE.

These records are used for testing record-level access.

## Step 7 – Elevate Security Admin

Before creating the ACLs, the security_admin role is elevated in ServiceNow.

This provides the required security administration access for creating and configuring Access Control Lists.

## Step 8 – Create Read ACL

A record-level Read ACL is created for the Institution Details table.

Configuration:

* Type: record
* Operation: read
* Name: u_institution_details
* Active: true
* Advanced: true
* Requires role: bb1
* Data condition: Branch is EEE

The following script is configured:

```javascript
(function () {
    // Allow admin users full access
    if (gs.hasRole('admin')) {
        return true;
    }

    // Allow only EEE branch users to see EEE records
    if (gs.hasRole('bb1')){
        return true;
    }

    // Deny access for all others
    return false;
})();
```

## Step 9 – Create ACL

A record-level Create ACL is created.

Configuration:

* Type: record
* Operation: create
* Name: u_institution_details
* Active: true
* Requires role: bb2
* Data condition: None

This ACL controls record creation.

## Step 10 – Create Write ACL

A record-level Write ACL is created.

Configuration:

* Type: record
* Operation: write
* Name: u_institution_details
* Active: true
* Requires role: bb3
* Data condition: None

This ACL controls record editing.

## Step 11 – Create Delete ACL

A record-level Delete ACL is created.

Configuration:

* Type: record
* Operation: delete
* Name: u_institution_details
* Active: true
* Requires role: bb4
* Data condition: None

This ACL controls record deletion.

## Step 12 – Development Verification

After creating the ACLs, the configurations are checked to make sure:

* The correct table is selected.
* The correct operation is selected.
* The required role is assigned.
* The Read ACL has the required data condition.
* The Read ACL contains the advanced script.
* All ACLs are active.

## Development Result

The ServiceNow project is developed with separate access controls for Read, Create, Write, and Delete operations.

The implementation prepares the system for the testing phase, where different users and roles will be impersonated to verify the expected access behavior.
