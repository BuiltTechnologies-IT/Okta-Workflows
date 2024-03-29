# Adobe User Management
<p align="center">
    <img width="100%" src="/Adobe%20User%20Management/assets/images/aum_hander_Overview.png" alt="overview"/>

## Summary
Given that Adobe does not offer a SCIM API, we decided that we would build a workflow to mimmoc the behaviors of a SCIM API using a variety of Okta Triggers and the Adobe User Management API. While Okta does provide a pre-built connector for the Adobe User Management API, many may find it challenging to build reliable triggers that mimmic that of the SCIM standard.

## What's in the Box?
This folder contains two flos:
1. `Adobe - Create/Update/Manage User`
- This is the primary flo that handles all actions of a traditional SCIM connector in a single flo. It uses if/else/if logic to track triggers from upstream flos and take a corresponding action.
2. `Adobe - Remove from Groups`
- This is a helper flow that cleans up any left over group assignments in Okta when the user is removed from the application assignment group (app_adobe_users).

## Setup
To use this flo, you will need to establish the following flos as triggers:

- `Trigger` - User removed from group (Okta)
- `Trigger` - User added to a group (Okta)
- `Trigger` - User profile updated (Okta)

> :bulb: **Tip:** Reminder that you must have a `VIP` Account with Adobe to access the Adobe User Management API

Also, you can follow Okta's [docs](https://built.workflows.okta.com/app/help/wf/en-us/Content/topics/workflows/connector-reference/adobeusermanagement/overview/authorization.htm) for setting up the Adobe User Management API.

<details>
<summary>
  Screenshots
</summary>

<p align="center">
    <img width="49%" src="/Adobe%20User%20Management/assets/images/aum-userAssigned.png" alt="overview"/>
&nbsp;
    <img width="49%" src="/Adobe%20User%20Management/assets/images/aum-userRemoved.png" alt="data-models"/>
</p>

<p align="center">
    <img width="49%" src="/Adobe%20User%20Management/assets/images/aum-userGroupAdded.png" alt="overview"/>
&nbsp;
    <img width="49%" src="/Adobe%20User%20Management/assets/images/aum-userGroupRemoved.png" alt="data-models"/>
</p>

<p align="center">
    <img width="49%" src="/Adobe%20User%20Management/assets/images/aum-userProfileUpdate.png" alt="overview"/>
&nbsp;
    <img width="49%" src="/Adobe%20User%20Management/assets/images/aum_hander_Overview.png" alt="data-models"/>
</p>

<p align="center">
    <img width="49%" src="/Adobe%20User%20Management/assets/images/aum_hander_Overview.png" alt="overview"/>
&nbsp;
    <img width="49%" src="/Adobe%20User%20Management/assets/images/aum_hander_Overview.png" alt="data-models"/>
</p>

</details>

## Contributors

<!---
npx contributor-faces --exclude "*bot*" --limit 70 --repo "https://github.com/amplication/amplication"

change the height and width for each of the contributors from 80 to 50.
--->

[//]: contributor-faces
<a href="https://github.com/wonderc0de"><img src="https://avatars.githubusercontent.com/u/139813346?v=4" title="yuval-hazaz" width="50" height="50"></a>

## License
