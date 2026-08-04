# SNAF Module 5: Configure Self-Service

## Overview
Covers where to configure Self-Service offerings (portals, knowledge, service catalog, and Virtual Agent), creating a knowledge base article by importing a Word document, approving articles for publishing, defining/applying/testing user criteria on the knowledge base, creating a Service Catalog Item using Catalog Builder, and using Workflow Studio to leverage existing flows and create new ones.

## Labs

### Section 5.1: Knowledge Management
**User story:** As the Infinity HHD Testing Coordinator, work is needed with the Human Resources group to provide knowledge management guidelines for Infinity HHD testing articles. HR group members are granted appropriate permissions to create, review, and publish articles. Articles created on Infinity HHD testing must be secure and only accessible to Cloud Dimensions employees.

**5.1.1: Manage Knowledge Base and Create Articles**
- Created a knowledge base article by importing a Word document
- Approved the article for publishing
- Defined, applied, and tested user criteria on the knowledge base

### Section 5.2: Service Catalog
**User story:** As the Infinity HHD Product Owner, a simple way is needed for employees to order an Infinity HHD through the Service Catalog, to track orders and inventory in one convenient location.

**5.2.1: Create a Catalog Item**
- Created an Infinity service catalog item using the Catalog Builder experience
- Added item variables
- Modified an item variable to increase price based on the choice selected
- Validated the work with "Try It" and ordering in the Service Catalog

### Section 5.3: Workflow Automation
**User story:** As the Service Catalog manager, the procurement process for Infinity HHDs needs to be automated so employees receive their devices on time, including automated communication to the requester.

**5.3.1: Create a Flow Using Workflow Studio**
- Created a new flow from scratch
- Associated the flow with a Service Catalog item
- Tested the flow

## Key Concepts Reinforced
- Self-service capability spans multiple connected pieces: knowledge articles, the service catalog, and workflow automation, each serving a different part of the employee self-service journey
- Knowledge base security relies on user criteria, not just role-based access, to control who can see published content
- Catalog items can carry conditional logic (like pricing that changes based on a selected choice), not just static request forms
- Workflow Studio automates what happens after a catalog request is submitted, connecting the request itself to downstream actions like notifications
