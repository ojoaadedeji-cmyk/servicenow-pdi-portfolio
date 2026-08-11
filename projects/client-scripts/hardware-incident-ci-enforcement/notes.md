# Hardware Incident CI Enforcement

## Objective

Configure the ServiceNow Incident form so that when the Category is set to Hardware:

- Configuration Item becomes mandatory.
- A guidance message prompts the user to select the affected Configuration Item.
- The Incident cannot be submitted without a Configuration Item.

For non-Hardware incidents, the Configuration Item remains optional.

## Components Used

- UI Policy
- UI Policy Action
- Client Script
- Incident table
- Configuration Item reference field
- GlideForm

## Implementation

### UI Policy

Name: Hardware Incident Configuration Item Requirement

Table: Incident [incident]

Condition: `Category is Hardware`

Configuration:

- Active: Yes
- Global: Yes
- On load: Yes
- Reverse if false: Yes
- Order: 100

### UI Policy Action

Field: Configuration item

Configuration:

- Mandatory: True
- Visible: Leave alone
- Read only: Leave alone
- Clear field value: No

The UI Policy Action makes the Configuration Item mandatory when the Incident Category is Hardware.

### Client Script

Name: Hardware Incident Guidance

Table: Incident [incident]

Type: onChange

Field name: Category

UI Type: All

Active: Yes

The Client Script displays guidance when Hardware is selected as the Incident Category.

```javascript
function onChange(control, oldValue, newValue, isLoading, isTemplate) {
    if (isLoading || isTemplate) {
        return;
    }

    if (newValue == 'hardware') {
        g_form.showFieldMsg(
            'cmdb_ci',
            'Select the affected Configuration Item for this hardware incident.',
            'info'
        );
    } else {
        g_form.hideFieldMsg('cmdb_ci', true);
    }
}
```

When Category is Hardware, the script displays an informational message beneath the Configuration Item field.

When the Category changes away from Hardware, the message is removed.

## Testing

### Test 1: Hardware Incident Without Configuration Item

**Test data:**

* Caller: Beth Anglin
* Category: Hardware
* Configuration Item: Empty
* Short description: `Hardware incident validation test`

**Expected result:**

* Configuration Item becomes mandatory.
* The Hardware guidance message appears.
* Submission is prevented while Configuration Item is empty.

**Actual result:**

* Configuration Item became mandatory.
* The guidance message appeared.
* ServiceNow prevented submission and displayed the mandatory field warning for Configuration Item.

**Result:** PASS

### Test 2: Hardware Incident With Configuration Item

**Test data:**

* Caller: Beth Anglin
* Category: Hardware
* Configuration Item: MACBOOK-AIR-13
* Short description: `Hardware incident with CI test`

**Expected result:**

* Configuration Item remains mandatory.
* The Incident can be submitted because a Configuration Item has been selected.
* The selected Configuration Item is retained on the saved Incident.

**Actual result:**

* The Incident was submitted successfully.
* The selected Configuration Item remained associated with the saved Incident.

**Result:** PASS

### Test 3: Non-Hardware Incident

**Test data:**

* Caller: Beth Anglin
* Category: Software
* Configuration Item: Empty
* Short description: `Non-hardware incident test`

**Expected result:**

* Configuration Item remains optional.
* The Hardware guidance message does not appear.
* The Incident can be submitted without a Configuration Item.

**Actual result:**

* Configuration Item remained optional.
* No Hardware guidance message was displayed.
* The Incident was submitted successfully without a Configuration Item.

**Result:** PASS

## Technical Decision

An onSubmit Client Script named `Validate Hardware CI` was initially created to provide additional validation when Hardware was selected without a Configuration Item.

During testing, ServiceNow's native mandatory field validation already prevented submission because the UI Policy made Configuration Item mandatory.

The additional onSubmit Client Script therefore duplicated existing platform behaviour and was removed.

The final solution uses:

* UI Policy and UI Policy Action to enforce the mandatory field requirement.
* Hardware Incident Guidance Client Script to provide contextual guidance.
* Native ServiceNow validation to prevent submission when the mandatory field is empty.

## Key Learning

This project provided practical experience with:

* UI Policies and UI Policy Actions
* Client Scripts and onChange events
* GlideForm (`g_form`)
* Dynamic mandatory field behaviour
* Configuration Item references
* Contextual form guidance
* Native ServiceNow form validation
* Positive and negative functional testing
* Avoiding unnecessary custom scripting

A key learning was that ServiceNow's declarative configuration should be used where it already satisfies the requirement. Custom scripting should add necessary functionality rather than duplicate native platform behaviour.
