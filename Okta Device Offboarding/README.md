<h1 align="center">
    <a href="https://getbuilt.com/#gh-light-mode-only">
    <img width="25%" src="https://github.com/BuiltTechnologies-IT/Okta-Workflows/blob/main/Adobe%20User%20Management/assets/images/built-logo-light-mode.svg">
    </a>
    <a href="https://getbuilt.com/#gh-dark-mode-only">
    <img width="25%" src="https://github.com/BuiltTechnologies-IT/Okta-Workflows/blob/main/Adobe%20User%20Management/assets/images/built-logo-dark-mode.svg">
    </a>
</h1>

<p align="center">
  <i align="center">Courtesy of Built Technologies 🚀</i>
</p>

<p align="center">
    <img width="100%" src="/Okta%20Device%20Offboarding/assets/images/odo-header_overview.png" alt="overview"/>

## Summary
Okta treats devices and users as isolated objects, creating problems with deativated user identities remaining tied to active devices in Okta. As a best pratice, we deactivate and delete user devices during our offboarding process. These flows can be used to pull a list of devices associated with a user, ensure there are no active user identities using those devices, then deactivate and delete the devices from Okta.

## What's in the Box?
This folder contains three flos:
1. `Device Offboarding Search`
- This is the primary flo that handles all actions of a traditional SCIM connector in a single flo. It uses if/else/if logic to track triggers from upstream flos and take a corresponding action.
2. `Okta Device Removal`
- This is a helper flow that cleans up any left over group assignments in Okta when the user is removed from the application assignment group (app_adobe_users).
3. `Delete Okta Device`
- This is a helper flow that cleans up any left over group assignments in Okta when the user is removed from the application assignment group (app_adobe_users).

## Setup
To use this flo, you will need to establish the following flos as triggers:

- `Trigger` - User deativated (Okta)

> :bulb: **Tip:** Reminder that you must have a `VIP` Account with Adobe to access the Adobe User Management API

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
