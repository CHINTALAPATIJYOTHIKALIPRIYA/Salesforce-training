1. What is SOQL?
SOQL (Salesforce Object Query Language) is a language used to read data stored in a Salesforce database. It allows developers to construct simple but powerful queries to search for specific records within a single object or across related objects. Unlike standard SQL, it is strictly for data retrieval (SELECT statements) and does not support data manipulation directly within the query.

2. What is an Apex Trigger?
An Apex Trigger is a script that executes before or after specific data manipulation language (DML) events occur. These events include inserting, updating, deleting, or undeleting records. Triggers allow developers to perform custom actions or complex business logic that cannot be achieved using standard point-and-click tools.

3. Key Differences
Flow vs. Trigger
Flow: A declarative (no-code) tool used for automating business processes. It is generally easier to maintain and is recommended for most standard automation.

Trigger: A programmatic (code) tool used for high-scale, high-complexity logic or scenarios that require features not yet supported by Flows.

Before vs. After Trigger
Before Trigger: Used to update or validate record values before they are saved to the database.

After Trigger: Used to access field values that are set by the system (like a Record ID or LastModifiedDate) and to affect changes in related records.

4. Your Trigger Use Cases
Postal Code Sync: Automatically updating a Shipping Address to match a Billing Address when a "Match" checkbox is selected.

Task Creation: Automatically creating a follow-up task for a sales representative whenever an Opportunity stage is set to "Closed Won".

Data Validation: Preventing the deletion of an Account if it still has active associated Cases.

Automatic Field Mapping: Pulling specific data from a Parent Account into a newly created Child Contact.

Status Propagation: Updating the status of all "Contact" records to "Inactive" when their parent "Account" is deactivated.

5. Query Examples (English Logic)
"Get the Names and Emails of all Contacts where the Account name is 'Acme'."

"Find all Opportunities that have a Close Date in the current month and a Stage of 'Closed Won'."

"Retrieve the IDs of all Leads that do not have a phone number listed."

"Select the total number of Cases currently assigned to the 'Support Tier 1' queue."

"Get the First Name and Last Name of all Contacts associated with Accounts in the 'Technology' industry."

6. Reflection: Why Enterprise Systems React Automatically
Enterprise systems must react automatically to data changes to ensure data integrity and operational efficiency. Manual data entry is prone to human error; automation ensures that when one piece of information changes, all related records and downstream processes (like task assignments or notifications) are updated instantly and consistently.

->Reflective Questions
1. Why do systems need triggers? To handle complex logic and cross-object interactions that require programmatic precision.

2. Difference between polling and event-driven systems? Polling checks for changes at set intervals (even if nothing changed), while event-driven systems (like triggers) only act when a specific event occurs, saving resources.

3. Why are database queries important? They allow the system to fetch only the necessary data required for a specific process, improving performance.

4. When should Flows be preferred over Triggers? Whenever the business logic is standard and can be handled without code, making it easier for non-developers to manage.

5. What problems happen if automation logic becomes too complex? It can lead to "infinite loops" (recursion), slow system performance, and make troubleshooting extremely difficult.

6. Why should developers think carefully before automating actions? Over-automation can lead to unintended data changes or system locks; it is essential to ensure automation adds value without creating technical debt.
