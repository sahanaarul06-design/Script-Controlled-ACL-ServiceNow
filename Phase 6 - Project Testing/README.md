# Phase 6 - Project Testing

## Project Title

Script-Controlled ACL – Restrict Record Access Based on Field Value

## Testing Overview

The project is tested to verify whether the Script-Controlled ACLs correctly restrict access to Institution Details records according to user roles and the Branch field.

Different users are impersonated to verify Read, Create, Write, and Delete access.

## Test Environment

The testing is performed in the ServiceNow instance using:

* Institution Details table
* Table name: u_institution_details
* Branch values: ECE, EEE, CSE
* Roles: bb1, bb2, bb3, bb4
* Administrator account
* EEE User account

## Test Case 1 – EEE User Read Access

The EEE User is impersonated and the Institution Details list is opened.

The user is checked for access to the available records.

### Expected Result

The EEE user should be able to view the permitted EEE branch records according to the configured Read ACL.

### Actual Result

The access behavior is checked against the configured Read ACL and the Branch condition.

## Test Case 2 – User Without Required Role

A user who does not have the required role is used for testing.

The Institution Details list is opened.

### Expected Result

The user should not be able to access the protected records because the required ACL role is not available.

### Actual Result

The access restriction is verified in ServiceNow.

## Test Case 3 – Administrator Access

The impersonation is ended and the administrator account is used.

The Institution Details list is opened.

### Expected Result

The administrator should have full access to the records.

### Actual Result

The administrator's access is verified.

## Test Case 4 – Create Access

The Create ACL is tested using a user with the required bb2 role.

The Institution Details list is opened and the New option is checked.

### Expected Result

A user with the required Create permission should be able to create a new record.

### Actual Result

The New option and record creation are verified.

## Test Case 5 – Write Access

The Write ACL is tested using a user with the required bb3 role.

An existing permitted record is opened and the Edit functionality is checked.

### Expected Result

The authorized user should be able to modify the record.

### Actual Result

The record editing capability is verified.

## Test Case 6 – Delete Access

The Delete ACL is tested using a user with the required bb4 role.

An existing permitted record is selected for deletion.

### Expected Result

The authorized user should be able to delete the record.

### Actual Result

The delete operation is verified.

## Test Case 7 – Combined Role Testing

The EEE User is tested with the assigned roles:

* bb1 – Read
* bb2 – Create
* bb3 – Write
* bb4 – Delete

### Expected Result

The user should be able to perform the operations permitted by the configured ACLs.

## Test Evidence

Screenshots should be captured for important testing stages, including:

* EEE User impersonation
* Institution Details list
* EEE branch records
* Restricted access
* Administrator access
* New record option
* Record editing
* Record deletion
* ACL configuration where required

## Testing Summary

The testing phase verifies that the ServiceNow ACL configuration works according to the project requirements.

The tests cover user roles, Branch-based access, administrator access, and the four CRUD operations.

## Testing Outcome

The project demonstrates how ACLs can be tested using different users and roles to control access to ServiceNow records.

The testing results are documented with screenshots and will be included in the final project documentation.
