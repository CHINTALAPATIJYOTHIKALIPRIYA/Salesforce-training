Day 10 Mini-Project: Enterprise Software System

1. System Overview
Provide a high-level summary of the mini-project. 
- Purpose: What business problem does this application or module solve?
- Core Functionality: Briefly list the primary features implemented in this system.
- Target Users: Who interacts with this system (e.g., Sales Reps, Support Agents, Managers)?



2. CRM Concepts
Explain the Customer Relationship Management (CRM) principles applied in this project.
- Core Concepts Used: (e.g., Lead Management, Account and Contact Management, Opportunity Tracking, Case Management).
- Business Value: How does automating this specific workflow improve business efficiency, user productivity, or customer satisfaction?



3. Data Model
Describe the underlying database structure or object relationships built for this project.

Objects and Fields:
- Account (Standard Object): Key fields include Name, Industry, Annual Revenue. Tracks company information.
- Contact (Standard Object): Key fields include FirstName, LastName, Email, Phone. Tracks individuals linked to Accounts.
- Custom Object (Custom Object): Key fields include Status, Total Amount. Describe its specific purpose here.

Relationships:
- Object A has a Lookup or Master-Detail relationship to Object B because of a specific business logic.



4. Validation Rules
List the rules implemented to ensure data integrity and cleanliness.

Rule Name: Restrict Invalid Status
- Description: Prevents users from moving a record to a final status without required information.
- Error Condition Formula: AND(ISPICKVAL(Status, "Completed"), ISBLANK(Required_Field))
- Error Message: You cannot complete this record without filling out the required field.



5. Flows
Detail the declarative automation (low-code logic) built using flows.

Flow Name: Automate Task Creation
- Trigger Type: Record-Triggered Flow (After Save) on Object Name.
- Condition: When Status changes to "High Priority".
- Actions: Automatically creates a follow-up Task assigned to the record owner.



6. Apex Logic
Document any programmatic backend code or triggers written for complex business logic.

Triggers and Classes:
- Class Name: AccountHandler
- Method: applyDiscounts(List Account accounts)
- Logic Description: Calculates custom tiered discounts for accounts based on their annual revenue using advanced conditional loops that exceed declarative capabilities.


7. UI Screens
Provide an overview of the user interface layout.

- Layout Configurations: Mention any custom Lightning Pages, Page Layout modifications, or Record Types used to tailor the UI for different user profiles.
- Screenshots: Insert the names or links of your UI screenshots here if applicable.



8. Complete Data Flow
Explain step-by-step how data moves through the entire system from input to final processing.

Step 1. Input: The user enters record details on the custom UI screen.
Step 2. Validation: The system runs Validation Rules to verify data correctness.
Step 3. Declarative Automation: Upon successful save, a Flow triggers to update related records.
Step 4. Programmatic Logic: An Apex Trigger executes to handle complex calculations.
Step 5. Final State: The database updates securely, and the UI dynamically refreshes to display updated metrics.



9. Reflection
What did you realize about enterprise software systems?

- Complexity and Scalability: Enterprise systems must be built with a solid architecture to handle large volumes of data while keeping the system organized and maintainable.
- Declarative versus Programmatic Balance: Realized that leveraging low-code tools like Flows and Validation Rules first keeps the system easy to maintain, while reserving Apex for heavy programmatic lifting.
- Data Integrity: Witnessed firsthand how critical rigorous data validation and structured data modeling are to avoiding messy databases and broken automations.
