\# VIP Incident Escalation



\## Project Date



10 August 2026



\## Environment



ServiceNow Personal Developer Instance (PDI)



Release: Australia



\## Project Objective



Create a Business Rule that automatically escalates an Incident when the caller is marked as a VIP.



\## Business Requirement



When an Incident is created or updated and the caller is a VIP, the system should automatically:



1\. Set Impact to High.

2\. Set Urgency to High.

3\. Allow ServiceNow to calculate the resulting Priority.



The Business Rule should not apply the escalation logic when the caller is not a VIP.



\## Implementation



\### Business Rule



Name: VIP Incident Escalation



Table: Incident \[incident]



Type: Before Business Rule



Insert: Enabled



Update: Enabled



Advanced: Enabled



Order: 100



\### Condition



Caller > VIP > is > true



The condition uses dot walking to access the VIP field on the User record referenced by the Incident's Caller field.



\### Script



```javascript

(function executeRule(current, previous) {



&#x20;   current.setValue('impact', 1);

&#x20;   current.setValue('urgency', 1);



})(current, previous);

