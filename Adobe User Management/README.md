# Adobe User Management
Author: Ty Kelley
Company: Built Technologies - getbuilt.com

## Summary
Given that Adobe does not offer a SCIM API, we decided that we would build a workflow to mimmoc the behaviors of a SCIM API using a variety of Okta Triggers and the Adobe User Management API. While Okta does provide a pre-built connector for the Adobe User Management API, many may find it challenging to build reliable triggers that mimmic that of the SCIM standard.

## What's in the Box?
This folder contains two flos:
1. Adobe - Create/Update/Manage User
- This is the primary flo that handles all actions of a traditional SCIM connector in a single flo. It uses if/else/if logic to track triggers from upstream flos and take a corresponding action. To use this flo, you will need to establish the following flos as triggers.
> Trigger - User removed from group (Okta)
> Trigger - User added to a group (Okta)
> Trigger - User profile updated (Okta)
2. Adobe - Remove from Groups