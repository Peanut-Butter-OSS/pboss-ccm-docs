Framework
=========

FURPS+
------
FURPS+ is a classication system used to guide the identification of functional and non-functional software requirements.
The model, developed at Hewlett-Packard was first publicly elaborated by Grady and Caswell. FURPS+ is now widely used in the software industry. 
FURPS is an acronymn where each letter represents a type of requirement:

* Functionality
* Usability (UX)
* Reliability 
* Performance
* Supportability
* The + was later added to extend the acronym to emphasize various attributes.

References:
* https://en.wikipedia.org/wiki/FURPS

User Stories
------------
User stories are short, simple descriptions of a feature told from the perspective of the person who 
desires the new capability, usually a user or customer of the system. 

They typically follow a simple template:
As a < type of user >, I want < some goal > so that < some reason >.

User stories will be defined as stories in the project's backlog.

References: 
* https://www.mountaingoatsoftware.com/agile/user-stories

Acceptance Criteria
-------------------
For each user story is set of Acceptance Criteria will defined. These acceptance criteria represents the complete definition of system requirements 

Each Acceptance criterium will be defined using the GIVEN-WHEN-THEN template.

The Given-When-Then formula is a template intended to guide the writing of acceptance tests for a User Story:

* (Given) some context
* (When) some action is carried out
* (Then) a particular set of observable consequences should obtain

For example:

* Given my bank account is in credit, and I made no withdrawals recently,
* When I attempt to withdraw an amount less than my card's limit,
* Then the withdrawal should complete without errors or warnings

Acceptance criteria will be defined using Cucumber