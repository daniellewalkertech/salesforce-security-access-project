# Business Requirements

## Project Scenario

A growing organization needs a Salesforce security model that protects sensitive customer and business information while allowing employees to access the records and functionality required for their roles.

The organization includes executive leadership, sales, customer support, accounts receivable, recruiting, and compliance-related users.

## Business Requirements

### 1. Establish a Secure Baseline

Organization-Wide Defaults should restrict record access by default so users only receive additional access when there is a legitimate business requirement.

### 2. Configure Organizational Visibility

A role hierarchy should reflect the company's reporting structure and allow appropriate upward visibility for managers and executives.

Roles include:

- CEO
- VP of Services
- Accounts Receivable
- Customer Support Director
- Customer Support Representative
- Sales Engineer
- Recruiter

### 3. Provide Additional Functional Access

Permission Sets should provide users with additional permissions without unnecessarily modifying their base profiles.

The organization requires permission sets for:

- Sales Orders
- Sales Contracts

These permissions should also be grouped where appropriate using the `Sales_Processing` Permission Set Group.

### 4. Share Won Opportunities

Opportunities that have been won should be shared with Accounts Receivable so the team can complete billing and financial processing activities.

### 5. Share High-Risk Cases

Cases associated with audit or compliance concerns should be shared with the designated compliance team for review and follow-up.

### 6. Support Account Collaboration

Account Teams should allow multiple employees to collaborate on the same customer account while maintaining controlled access.

### 7. Support Exceptions

Manual sharing should be available when an individual record must be shared with a specific user outside the normal sharing model.

## Success Criteria

The Salesforce security model should:

- Protect records from unauthorized access
- Provide users with the minimum access required to perform their jobs
- Allow controlled exceptions through sharing mechanisms
- Separate object permissions from record-level access
- Support collaboration without unnecessarily opening organization-wide access
