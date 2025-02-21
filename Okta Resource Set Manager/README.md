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
    <img width="100%" src="/Okta%20Resource%20Set%20Manager/assets/helperTriggerAddResourceToSet.png" alt="overview"/>

## Summary
Currently, there's not a built-in way to automate Okta Resource Sets within the UI. This can make these Resource Sets very hard to manage when dealing with hundereds of resources within any given category. For our specific use case, we needed a way to segment the ability to edit users for all groups with an "org_" prefix, as these are automated from user profile data (mastered by our HRIS) and should not be manually changed.

This flowpack includes a set of flows (and a table) that create the ability to building rules that automate the additions of groups to resource sets based on simple regex statements. Currently it's set up to be triggered by the "Group Created" Okta trigger, but it is configured to easily add support for any other resoure type.

## What's in the Box?
This folder contains three flows and one table:
1. `Helper Trigger - Add Resource to set`
- This is the primary flow that pulls the table entries for the passed through resourceType, and passes them through the helper flows to be processed. It's set up as a helper flow that gets triggered when a resource is created. We use individual trigger flows for the main Okta triggers (Group Created, App Created, etc.) that are central triggers for all flows that utelize them, but you could adjust this to specifically be the trigger if you only wanted to focus on one resource type.

<div style="text-align: center;">
    <img style="padding-bottom: 10px; padding-top: 10px;" width="80%" src="/Okta%20Resource%20Set%20Manager/assets/helperTriggerAddResourceToSet.png" alt="overview"/>
</div>

2. `Filter Resource Table Results`
- This helper flow takes the row objects from the prior flow and validates the resource (currently the group) against the regex statement of each returned line from the table. If it matches the pattern, it returns true (which returns the object) and if not it ignores it.

<div style="text-align: center;">
    <img  style="padding-bottom: 10px; padding-top: 10px;" width="80%" src="/Okta%20Resource%20Set%20Manager/assets/filterResourceTableResults.png" alt="overview"/>
</div>

3. `Add Resource to Resource Set`
- This helper flow that processes all the items returned from the prior flow. It builds the api endpoint url based on the resourceType value (currently just set up for groups, but is built to be easily expanded to other resourceTypes), replaces the {{resourceId}} placeholder with the actual resourceId, does the same thing with the resource set management endpoint, format's the additions object, then calls the ["Add more resources to a resource set"](https://developer.okta.com/docs/api/openapi/okta-management/management/tag/RoleCResourceSetResource/#tag/RoleCResourceSetResource/operation/addResourceSetResources) endpoint to add them to the resource set.

<div style="text-align: center;">
    <img  style="padding-bottom: 10px; padding-top: 10px;" width="80%" src="/Okta%20Resource%20Set%20Manager/assets/addResourceToResourceSet.png" alt="overview"/>
</div>

4. `Resource Set Automation Mapping`
- This table is where you'll enter in the resource set information (Name and ID), resourceType tied to it, and the regex statement for the resource filtering. Currently this is set up to only use a regex name match, but it could be adapted to use other resource atributes with an extra column to identify them, and an if/else statement in the `Filter Resource Table Results` table to handle them.

<div style="text-align: center;">
    <img  style="padding-bottom: 10px; padding-top: 10px;" width="80%" src="/Okta%20Resource%20Set%20Manager/assets/resourceSetAutomationMapping.png" alt="overview"/>
</div>

## Setup
To use this flow, you will need to:

- Establish a Group Created (Okta) trigger flow.
- Update the `Resource Set Automation Mapping` table with the information on the Resource Sets you want to manage.
- Update the Lookup table in the `Add Resource to Resource Set` flow with your own domain for the Okta api url.
- Update the authentication connector for the Okta - Custom API Action card.

> :bulb: **Tip:** Remember, you can add more resource types by adding new resource creation triggers and updating the Lookup card in the `Add Resource to Resource Set` flow.


## Contributors

[//]: contributor-faces
<a href="https://github.com/wellwellelle"><img src="https://avatars.githubusercontent.com/u/57826707?v=4" title="wellwellelle" width="50" height="50"></a>

## License
This project is licensed under the [MIT](./LICENSE) license.