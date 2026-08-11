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
