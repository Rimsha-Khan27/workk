Overview:

The ILS application supports non-production user access management through Active Directory (AD) groups and database-level provisioning for internal users across multiple environments.

Purpose:

The purpose of this document is to define the standard process for provisioning and modifying non-production user access for the ILS application.

Environment Supported:
QA/Test
Development
Non-PROD Environments

(You can also write DEV / TEST / QA if your manager prefers short format.)

Scope of Work:
New user provisioning
Existing user permission updates
AD group access management
Database-level user provisioning through DML scripts
User validation and notification process
Pre-requisite:
A ServiceNow request must be raised for user provisioning or access modification.
Required approvals must be completed before processing the request.
User details such as Name, Email Address, R1-Core LAN ID, Employee ID, Branch, User Group, and required environment access must be provided.
Mirror user details must be provided for access replication requests, if applicable.
Support personnel must have required access to Active Directory, ILS database, and Jenkins non-production pipeline.
