# Phase 1 - Brainstorming & Ideation

## Project Title
Script-Controlled ACL – Restrict Record Access Based on Field Value

## Project Idea

The project focuses on implementing record-level security in ServiceNow using Access Control Lists (ACLs) and scripts.

The main idea is to control access to Institution Details records based on the Branch field.

## Problem Identification

In an institution, student records may belong to different branches such as ECE, EEE, and CSE. Not every user should have access to all records.

Therefore, a security mechanism is required to restrict users from viewing or modifying records that they are not authorized to access.

## Proposed Idea

A Script-Controlled ACL is used to control access to records.

The project allows users belonging to the EEE branch to view EEE branch records, while administrators retain full access.

Different roles are used to control Create, Read, Write, and Delete operations.

## Main Objectives

- Restrict unauthorized access to records.
- Allow authorized EEE users to view EEE records.
- Provide administrators with full access.
- Demonstrate Script-Controlled ACL implementation.
- Understand record-level security in ServiceNow.
- Control Create, Read, Write, and Delete operations using roles.

## Roles Planned

- bb1 – Read access
- bb2 – Create access
- bb3 – Write access
- bb4 – Delete access

## Expected Outcome

The project should demonstrate how ServiceNow ACLs and scripts can be used to protect records based on user roles and field values.
