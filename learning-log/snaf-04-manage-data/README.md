# SNAF Module 4: Manage Data

## Overview
Covers evaluating requested application enhancements, ServiceNow database architecture and administration concepts, schema maps, table and field access controls, import sets, transform maps, core CMDB functionality, the CI Class Manager, the Common Services Data Model (CSDM), and Discovery/Service Mapping.

## Labs

### Section 4.1: Table Administration
**User story:** As the Infinity HHD Testing Coordinator, data needs to be stored to track the assignment of Infinity HHD devices used at Cloud Dimensions, to effectively support the pilot testing efforts.

**4.1.1: Create a Table for HHD Configuration Records**
- Created a new table
- Configured the list and table form views
- Updated the application menu and created new application modules

### Section 4.2: Application and Access Control
**User story:** As the Data Security Manager, access to the Infinity HHD application menu and modules needs to be restricted. Incident records need to be secured so only the Service Desk and Training Technology group can view and update them, and the Asset Tag field needs specific access controls defined.

**4.2.1: Create Access Controls**
- Provided application menu and module access for a specified role
- Created a new role
- Created Access Control rules to secure data at the table and field levels

### Section 4.3: Import Data
**User story:** As the Infinity HHD Manager, HHD registration data needs to be brought into the ServiceNow Platform, working with the System Administrator to import registration data currently held in an Excel spreadsheet.

**4.3.1: Import HHD Hardware Data**
- Created a new list layout to prepare for data import
- Created an import set table and transform map
- Transformed multiple imports
- Cleaned up import data

### Section 4.4: CMDB
**User story:** As the Configuration Manager, Infinity HHDs and their relationships with other configuration items need to be tracked to understand the impact of adding configuration items to existing infrastructure and improve visibility into potential problems.

**4.4.1: Explore Data Structures, CMDB, and CI Relationships**
- Explored Schema Maps
- Explored CMDB via CI Class Manager
- Explored the HHD CI in Class Manager
- Defined CI relationships between the HHD CIs and the Infinity HHD Service Offering
- Viewed the Dependency Map

## Key Concepts Reinforced
- Table administration (creating tables, configuring views, application modules) is the foundation that later access control and data import work builds on
- Access control operates at multiple levels simultaneously: application/module visibility (role-based), and table/field-level data security (ACLs)
- Data import (import sets, transform maps) is the standard path for bringing external data, like a spreadsheet, into ServiceNow's data model in a structured, repeatable way
- CMDB relationships and dependency mapping give visibility into how a configuration item (like the HHD) connects to and impacts other parts of the infrastructure, not just its own record
