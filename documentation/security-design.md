# Salesforce Security Design

## Security Model Overview

This project uses a layered Salesforce security model designed to provide users with the minimum access required to complete their job responsibilities.

The security model separates:

- Object-level access
- Field-level access
- Record-level access
- Role-based visibility
- Exception-based sharing

## Organization-Wide Defaults

Organization-Wide Defaults establish the baseline level of record access.

The goal is to begin with restrictive access and then extend access only when a business requirement exists.

This follows the principle of least privilege.

## Role Hierarchy

The role hierarchy provides upward visibility within the organization.

Users higher in the hierarchy may gain access to records owned by users below them, depending on the object configuration.

Example roles include:

- CEO
- VP of Services
- Accounts Receivable
- Customer Support Director
- Customer Support Representative
- Sales Engineer
- Recruiter

The role hierarchy controls record visibility, not user permissions.

## Profiles

Profiles establish a user's baseline permissions.

Profiles can control:

- Object permissions
- Field-level security
- Login hours
- Login IP ranges
- App access
- Tab visibility

Profiles determine what a user can do within Salesforce.

## Permission Sets

Permission Sets provide additional permissions without changing the user's base profile.

This design uses permission sets for:

- Sales Orders
- Sales Contracts

This allows administrators to grant additional access only to users who need it.

## Permission Set Groups

The `Sales_Processing` Permission Set Group combines related permission sets into a single assignment.

This simplifies administration and makes access easier to manage.

## Sharing Rules

Sharing Rules extend record access beyond the Organization-Wide Default settings.

### Won Opportunities

Opportunities meeting the required business criteria are shared with Accounts Receivable.

This allows the finance-related team to access records needed for processing completed sales.

### High-Risk Cases

Cases involving audit-related concerns are shared with the designated compliance team.

This allows specialized users to review sensitive cases without opening access to all users.

## Manual Sharing

Manual Sharing provides record-level access for individual exceptions.

This is useful when:

- One user needs temporary access
- A specific record requires collaboration
- A sharing rule would be too broad

Manual sharing should be used for exceptions rather than organization-wide access strategies.

## Account Teams

Account Teams allow multiple users to collaborate on customer accounts.

Different team members can receive different levels of access based on their responsibilities.

This supports collaboration while maintaining controlled record access.

## Security Decision Framework

When designing access, the following order should be considered:

1. Profile
2. Permission Set
3. Organization-Wide Defaults
4. Role Hierarchy
5. Sharing Rules
6. Teams
7. Manual Sharing

## Key Principle

Permissions answer:

**What can the user do?**

Sharing answers:

**Which records can the user access?**

A secure Salesforce environment requires both permission management and record-level access controls.

## Design Goal

The final security model should provide enough access for users to perform their responsibilities without exposing unnecessary data.

This supports:

- Least privilege
- Data protection
- Controlled collaboration
- Easier administration
- Scalable user access management
