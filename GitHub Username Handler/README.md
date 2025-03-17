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
Many of the GitHub cards in Okta Workflows (as well as general api actions) require identifying the user with the "login" (username) of their linked account. For Enterprise accounts who aren't using Enterprise Managed Users (EMUs), this is an issue since there isn't an easy way to view the linked account information for users in their organization. This flow helps solve that by pulling the linked account username from a graphql query, which is one of the only ways to get this through the api.

> :warning: For the most part the standard rest endpionts don't have a way to pull this info with the exception of a single option that requires a legacy personal token from a top level enterprise admin... which isn't great.

## What's in the Box?
This folder contains six core flows:
1. `Trigger - Github Linked Account Manager`
2. `Paginate Github`
3. `Check App User Profile for matching login`
5. `Format Results List`
6. `Format Results List - Segment Statuses`

## Setup
Notes included in `Trigger - Github Linked Account Manager`

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