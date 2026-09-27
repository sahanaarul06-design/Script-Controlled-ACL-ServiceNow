# Phase 4 - Project Planning

## Project Title

Script-Controlled ACL – Restrict Record Access Based on Field Value

## Planning Overview

The project is planned as a step-by-step ServiceNow implementation of Script-Controlled Access Control Lists.

The plan covers user creation, role creation, table configuration, record creation, ACL configuration, testing, documentation, and final demonstration.

## Step 1 – User Planning

A test user named EEE User will be created for testing the access restrictions.

User details:

* User ID: EEE User
* First Name: EEE
* Last Name: User
* Email: [eeeuser@gmail.com](mailto:eeeuser@gmail.com)

## Step 2 – Role Planning

Four roles will be created and assigned for testing different operations:

* bb1 – Read
* bb2 – Create
* bb3 – Write
* bb4 – Delete

The roles will be used to verify that each ACL operation works as expected.

## Step 3 – Table Planning

A custom table will be created with the following details:

* Label: Institution Details
* Name: u_institution_details
* Extends for: False

The table will store student information and branch details.

## Step 4 – Field Planning

The following fields will be created:

* Student Roll Number – Auto Number
* Student Name – Reference - User
* Faculty Name – Reference - User
* Branch – Choice
* Email – String
* Phone Number – String
* Description – Multi String

The Branch field will contain:

* ECE
* EEE
* CSE

## Step 5 – Record Planning

Multiple records will be created in the Institution Details table.

Records with ECE, EEE, and CSE branch values will be used to test the record-level access restrictions.

## Step 6 – ACL Planning

Four record-level ACLs will be planned:

### Read ACL

* Operation: Read
* Required role: bb1
* Data condition: Branch is EEE
* Advanced script: Yes

### Create ACL

* Operation: Create
* Required role: bb2
* Data condition: None

### Write ACL

* Operation: Write
* Required role: bb3
* Data condition: None

### Delete ACL

* Operation: Delete
* Required role: bb4
* Data condition: None

## Step 7 – Security Administration

The security_admin role will be elevated before creating and configuring the ACLs.

The ACL configurations will be reviewed after creation to ensure that the correct table, operation, role, and conditions are selected.

## Step 8 – Testing Plan

The project will be tested using ServiceNow impersonation.

The following scenarios will be checked:

1. EEE User can access the permitted EEE records.
2. A user without the required role cannot access the protected records.
3. Administrator can access all records.
4. Users with the required Create role can create records.
5. Users with the required Write role can edit records.
6. Users with the required Delete role can delete records.

## Step 9 – Documentation Plan

Screenshots will be captured during the important implementation and testing stages.

The documentation will include:

* User creation
* Role creation
* Table creation
* Field configuration
* Sample records
* Read ACL
* Create ACL
* Write ACL
* Delete ACL
* Impersonation testing
* Final results

## Step 10 – Final Submission Plan

The project will be organized phase-wise in the GitHub repository.

The repository will contain separate folders for all eight project phases.

The final demonstration will explain the project objective, implementation, ACL configuration, testing process, and expected outcome.

## Expected Outcome

The planned implementation should demonstrate how ServiceNow ACLs can control access to records based on roles and field values.

The completed project should provide a clear demonstration of record-level security and CRUD access control.
