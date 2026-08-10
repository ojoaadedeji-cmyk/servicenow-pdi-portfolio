# VIP Incident Escalation

## Project Date

10 August 2026

## Environment

ServiceNow Personal Developer Instance (PDI)

Release: Australia

## Project Objective

Create a Business Rule that automatically escalates an Incident when the caller is marked as a VIP.

## Business Requirement

When an Incident is created or updated, and the caller is a VIP, the system should automatically:

1. Set Impact to High.
2. Set Urgency to High.
3. Allow ServiceNow to calculate the resulting Priority.

The Business Rule should not apply the escalation logic when the caller is not a VIP.

## Implementation

### Business Rule

Name: VIP Incident Escalation

Table: Incident [incident]

Type: Before Business Rule

Insert: Enabled

Update: Enabled

Advanced: Enabled

Order: 100

### Condition

Caller > VIP > is > true

The condition uses dot walking to access the VIP field on the User record referenced by the Incident's Caller field.

### Script

```javascript
(function executeRule(current, previous) {

    current.setValue('impact', 1);
    current.setValue('urgency', 1);

})(current, previous);
```

## Testing

### Test 1: VIP Caller

**Test objective:**  
Verify that the Business Rule escalates an Incident when the caller is marked as a VIP.

**Test data:**

Short description: `VIP caller escalation test`

Caller: VIP user

**Expected result:**

Impact = 1 High

Urgency = 1 High

Priority = 1 Critical

**Actual result:**

Impact = 1 High

Urgency = 1 High

Priority = 1 Critical

**Result:** PASS


### Test 2: Non VIP Caller

**Test objective:**  
Verify that the Business Rule does not escalate an Incident when the caller is not marked as a VIP.

**Test data:**

Short description: `Non VIP caller escalation test`

Caller: Non VIP user

**Expected result:**

The Business Rule should not apply the VIP escalation logic.

**Actual result:**

The VIP Business Rule did not escalate the Incident.

**Result:** PASS

### Key Learning

Business Rules can be used to automate server-side actions when specified conditions are met.

The exercise provided practical experience with:

- Business Rules
- Before Business Rule execution
- Server-side scripting
- Reference fields
- Dot walking
- Incident management
- VIP users
- Impact and Urgency
- Priority calculation
- Testing conditional automation
