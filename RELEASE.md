# Release Methodology

## Deploy Pipeline Overview
Agilepoint has 3 seperate environments and its own integrated source control process. 
- Agilepoint developers modify code initially in the development environment and when ready to test, publish in the development environment,
- when ready, code is exported from the development environment and imported into the test environment. To allow stakeholder to see the code changes, the application is publisedh in the test environment,
- when stakeholders approve, code is exported from the test environment and imported into the production environment. To allow the intended audience to use the update form, the application is published in the production environment.

Once the developer publishes an app in the Agilepoint production environment and the app is verified to be working, the developer:
- navigates into "Build Apps" in Agilepoint and selects the application,
- note the current (production) version number (e.g. 1.05),
- exports the app (a zip file) and saves locally,
- finally, imports the zip file into the correct folder in the AgilePoint repo in Github.

## Lead Developer: Tag and release `Production` branch
After the app is published in production on Agilepoint and loladed into Github, the lead developer must tag and release the `main` branch so that the 
Project Manager/s can complete their Release Notes.
1. goto the [release section](https://github.com/CityOfBoston/AgilePoint/releases) of the repository,
2. click the "Draft a New Release" button
3. click on "Choose a Tag" and create a new tag in the format "APPName_vn.nn" where _vn.nn_ is the version number assigned when publishing in Agilepoint.
5. ensure the Target is the `main` branch
5. give the release a title (same as the tag name)
6. in the Description, copy and paste in the template below, then click the `Generate release notes` button to append the commits to be bottom of the textbox. Update the "Jira Tickets` section with all tickets that have been addressed in this release. Update the "Agilepoint Version" section with the associated version generated when publishing the app in Agilepoint.
7. click "Set as the latest release",
8. click the `Save draft` button.

## Project Manager: Release `Production` branch
The Project Manager will edit the draft release notes, finalize and publish them.
1. goto the [release section](https://github.com/CityOfBoston/AgilePoint/releases) of the repository,
2. edit the latest draft release,
3. update the *[PM to complete]* block with narrative related to the release,
4. click "Set as the latest release",
5. click the `Publish release` button.

A Github action <img src="https://s3-us-west-2.amazonaws.com/slack-files2/bot_icons/2023-02-09/4779927044435_48.png" alt="" style="width: 20px; height: 20px"/> will now fire which will post a message to the slack [#jira-releases channel](https://cityofboston-doit.slack.com/archives/C03UZ01E5N2).

# Release Description Template 
```
## [Copy title of production PR]

### Release Notes
[PM to complete]

### Related Jira tickets
[Add a list of Jira Tickets addressed in this Release, with links to the Jira website]
example: Dig-1839 - [Update residential exemption application in Assessing Online](https://bostondoit.atlassian.net/browse/DIG-1839)

### Agilepoint Version
[add in the AGP version]
```
## Project Manager: Release Jira Tickets 
1. In Jira create a release with the following convention RepositoryName/release version (e.g. Appname/v9.2023.2) 
2. The release description should include what was updated and a link to the release notes (e.g. Rental Relief updates[Release Notes](https://github.com/CityOfBoston/AgilePoint/releases/tag/v9.2023.2))
3. Attached release fix version to tickets before releasing the tickets. 
