# What is OWASP?
The Open Web Application Security Project (OWASP) is an international non-profit organization dedicated to web application security. OWASP API Security Top Ten and Beyond! is meant to help improve the skills of bug bounty hunters, developers, penetration testers, organizational leadership, and anyone else interested in learning about API security.

## Course Objectives
The OWASP API Security Top 10 is a list of the most critical security risks for Application Programming Interfaces. Develop a strong foundation in the following API security risks:
* **API1:2023 :** Broken Object Level Authorization
* **API2:2023 :** Broken Authentication
* **API3:2023 :** Broken Object Property Level Authorization
* **API4:2023 :** Unrestricted Resource Consumption
* **API5:2023 :** Broken Function Level Authorization
* **API6:2023 :** Unrestricted Access to Sensitive Business Flows
* **API7:2023 :** Server Side Request Forgery
* **API8:2023 :** Security Misconfiguration
* **API9:2023 :** Improper Inventory Management
* **API10:2023 :** Unsafe Consumption of APIs

## API1:2023 Broken Object Level Authorization
### Description
BOLA vulnerabilities occur when an API provider does not have sufficient controls in place to enforce authorization. In other words, API users should only have access to sensitive resources that belong to them. When BOLA is present an attacker will be able to access the sensitive data of other users. Example:
* GET /api/user/1
* GET /user/account/find?user_id=aE1230000token
* POST /company/account/Apple/balance
* GET /admin/settings/account/bman

### Preventative Measures
In order to improve API security, it is important to implement robust authorization controls. These controls should consider user policies and role-based access control hierarchies. The primary focus should be to ensure that authenticated users only have access to resources they are authorized to have access to. Using less predictable resource IDs can increase the challenge of a user or attacker guessing the resource IDs of other users. Developers should perform tests that specifically test authorization controls. 

* Implement a proper authorization mechanism that relies on the user policies and hierarchy.
* Use the authorization mechanism to check if the logged-in user has access to perform the requested action on the record in every function that uses an input from the client to access a record in the database.
* Prefer the use of random and unpredictable values as GUIDs for records' IDs.
* Write tests to evaluate the vulnerability of the authorization mechanism. Do not deploy changes that make the tests fail.