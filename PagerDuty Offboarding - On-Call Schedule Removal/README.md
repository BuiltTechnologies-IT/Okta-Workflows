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


## Summary
Without purchasing an extra SKU within PagerDuty (Advanced Permissions), there isn't any way to easily automate offboarding of users if they are attached to an on-call schedule. By default, their official SCIM connector will _only_ deactivate the user, but will keep them on the on-call rotation until you manually remove them. Additionally, there's no way to fully remove the user from the platform without removing them from all schedules. This presents a problem since the user is "deactivated" without any errors or issues on Okta's side, but actually still exists (and remains scheduled) on PagerDuty's side. These flows utilize the PagerDuty api endpoints that are available _without_ the additional SKU to check a user for any attached schedules, remove them, and notify their manager.

> :warning: This flow pack does include a handful of references to our internal "Built Bot" which handles our slack notifications and error handling. You'll need to replace any instances of the "Slackbot Placeholder" flow with your own notification/error handler.

## What's in the Box?
This folder contains six core flows, one additional utility, and a placeholder flow:
1. `Trigger - PagerDuty Offboarding`
- tbd
2. `Stream - Check Schedules for User`
- tbd
3. `Helper - Remove User from a Schedule`
- tbd
5. `For Each - Process Schedule Layers`
- tbd
6. `Helper - Delete User and Notify Manager`
- tbd

Additional Utility and Placeholder Flows:
1. `Recursive Manager Retrieval`
- tbd
2. `Slackbot Placeholder`
- tbd

## Setup
To use this flow, you will need to update the initial `User Assigned from Application` trigger card to point to your internal PagerDuty app in Okta. Additionally, you'll need to set up a connection for the PagerDuty connector in Okta Workflows.

<details>
<summary>
  Screenshots (to be added)
</summary>

</details>

## Contributors

<!---
npx contributor-faces --exclude "*bot*" --limit 70 --repo "https://github.com/amplication/amplication"

change the height and width for each of the contributors from 80 to 50.
--->

[//]: contributor-faces
<a href="https://github.com/wellwellelle"><img src="https://avatars.githubusercontent.com/u/57826707?v=4" title="wellwellelle" width="50" height="50"></a>

## License
This project is licensed under the [MIT](./LICENSE) license.