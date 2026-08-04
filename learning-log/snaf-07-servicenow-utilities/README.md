# SNAF Module 7: Introduction to ServiceNow Utilities

## Overview
Covers assessing when to use scripting, UI policies, and business rules, preparing update sets and migrating changes, and demonstrating awareness of developer tools, concepts, and testing resources.

## Labs

### Section 7.1: UI Policies and Business Rules
**User story:** As the Service Desk manager, specific support data needs to be required for Infinity HHD incidents to speed up resolution time for those participating in the pilot, working with the System Administrator to determine the best approach.

**7.1.1: Create a UI Policy and Business Rules**
- Created a UI Policy with UI Policy Actions
- Created Business Rules

### Section 7.2: Migration and Integration
**User story:** As a Release Manager, work is needed with the System Administrator to move configuration changes from one instance to another, to easily implement updates in the ServiceNow Platform.

**7.2.1: Create System Update Sets**
- Reviewed an Update Set in the Student Instance
- Created a new Update Set in the Student Instance
- Made configuration changes and captured them in a new Update Set
- Marked the Update Set complete and exported it

### Section 7.3: Applying an Update Set
**User story:** The department requested configuration changes to a form. They have been tested and are ready to be migrated. It's now time to retrieve, preview, and commit the appropriate update set.

**7.3.1: Migrate Changes**
- Retrieved an update set
- Previewed and committed platform changes

## Key Concepts Reinforced
- UI Policies and Business Rules serve different layers of enforcement: UI Policies control what's visible/mandatory on the form client-side, while Business Rules enforce logic server-side
- Update Sets are the mechanism for moving configuration changes between instances (e.g., dev to test to prod) in a controlled, trackable way
- Migrating a change is a multi-step process: capture (create/export the Update Set), then retrieve, preview, and commit on the target instance, not a single one-click action
