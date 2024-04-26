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

> :warning: **Unofficial API:** This workflow contains an undocumented API call. Undocumented API calls may be changed without notice.

## What's in the Box?
This folder contains three flos:
1. `Device Offboarding Search`
- This flow is the top-level helper flow which uses an unofficial API endpoint to get a list of devices assigned to a user in Okta. It then calls a helper flow to deactivate and delete each device reutned by the API call.
2. `Okta Device Removal`
- This helper flow is called for each device assigned to the user in Okta. The first part of the flow uses Okta's devices API to issue a List Devices call with expanded results that includes all users assigned to the device. The flow then checks to see if any of the users assigned to the device have a status of `ACTIVE`. This is important because devices in Okta have a many-to-many relationship, where many users can be tied to many devices. We don't want to deactivate or delete a device that is assigned to an active user in Okta. Once confirming the device has no active users, we then use the deactivate URL conveniently provided in the device object to deactivate the device. Finally, we call a helper flow to delete the device from Okta.
3. `Delete Okta Device`
- This flow will delete any device whos status is `DEACTIVATED` from Okta using the devices API.

## Setup
To use this flo, you will need to establish the following flos as triggers:

- `Trigger` - User deativated (Okta)

<details>
<summary>
  Screenshots
</summary>

<p align="center">
    <img width="49%" src="/Okta Device Offboarding/assets/images/(HT) Device Offboarding Search.svg" alt="overview"/>
&nbsp;
    <img width="49%" src="" alt="data-models"/>
</p>

<p align="center">
    <img width="49%" src="" alt="overview"/>
&nbsp;
    <img width="49%" src="" alt="data-models"/>
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
