---
title: Simple Form
description: User guide for creating a simple form in Altinn Studio
weight: 10
aliases:
- /altinn-studio/guides/basic-form/
---
The points below cover a minimum of what is required to create and publish a form on Altinn Studio.

{{% expandlarge id="create-service" header="Creating the service containing the form" %}}
New services are created from your service dashboard.

1. Click on the "Create new application" button at the top right of the screen.
2. Choose the _owner_ of the service from the dropdown list.
   - If you choose your own user, you will be able to test all functionality in Altinn Studio but will not have access to
     the test environment.
   - If you choose an _organization_ for which you have rights, you will also have the opportunity to publish the service to
     the organization's test environment.
3. Enter the name of the service.
   _{{% insert "content/altinn-studio/v8/_includes/concepts/service-name-vs-display-name.md" %}}_
4. Click the "Create application" button.

Once the service is created, you will be taken to the service overview page.

<video autoplay loop controls muted src="./create-service.mp4">Your browser does not support video playback.</video>
{{%/expandlarge%}}

{{% expandlarge id="set-service-name" header="Adding a display name for the service" %}}
The service needs a display name that appears as a heading on the form and in the user's inbox in Altinn.

Add a display name by:

1. Clicking on the "Settings" button in the top left menu bar.
2. Modifying the "Application name" field to the desired display name.

The change is saved as soon as you leave the field. Once the display name is changed, you can see that it has also been updated on
the overview page.

<video autoplay loop controls muted src="./set-service-name.mp4">Your browser does not support video playback.</video>
{{%/expandlarge%}}

{{% expandlarge id="create-datamodel" header="Creating a data model for the form" %}}
{{% insert "content/altinn-studio/v8/_includes/concepts/data-model-definition.md" %}}

A very simple data model with some example fields is included when creating a service. You can edit the field names
to make it clear what they represent and add your own fields.

1. Navigate to the "Data Model" page by clicking on "Data Model" in the top menu bar.
2. Click on a field to bring up editing options, e.g., to change the name of the field.
3. Click "Add new" and choose type. Relevant types for simple forms include, among others:
   - Text - text content, can be used for most fields.
   - Integer
   - Decimal
4. When you have finished adding fields, click the "Generate models" button.

If you want to group fields, you can add an "Object" and then add fields under that group.

<video autoplay loop controls muted src="./create-datamodel.mp4">Your browser does not support video playback.</video>
{{%/expandlarge%}}

{{% expandlarge id="create-form" header="Dragging form components into the form and configuring them" %}}
Forms are created in Altinn Studio by navigating to the "Build" page. On this page 

Forms are created by dragging desired form components into each individual form page.

### Adding fields to the form
{{% insert "content/altinn-studio/v8/_includes/reference/form-component-categories.md" %}}

1. Click on the page you want to edit. When creating a service, a page named "Page1" is automatically included.
2. Select a component from the panel on the left and drag it onto the page. The component is now active in the configuration panel and
   can be configured.
3. {{% insert "content/altinn-studio/v8/_includes/ui-patterns/bind-component-to-data-model.md" %}}
4. {{% insert "content/altinn-studio/v8/_includes/ui-patterns/add-text-to-component.md" %}}
5. Open the "Content" section in the configuration column to set up other configurations. Available configurations vary
   from component to component, but common to most are:
   - Whether the width of the component on the screen should be adjusted
   - Whether the component should be read-only

<video autoplay loop controls muted src="./create-form.mp4">Your browser does not support video playback.</video>

### Useful Information
- The button to submit the form must be added manually. Use the component called "Button".
- Add a new page by clicking on the "Add new page" button at the bottom of the page column.
- Edit page names by selecting the page, then click on the ID field to edit.
  - Add a display name for the page by opening the text section and adding "Display name for page".
- Buttons to navigate forward/backward between pages are added automatically when adding a page.
{{%/expandlarge%}}

{{% expandlarge id="configure-access-rules" header="Configuring access rules" %}}

{{% notice info %}}
We are working to simplify this setup, as there are many rules to deal with in the service template. We recommend following
the recipe below for now. Descriptions in this section will be updated continuously as we make changes.
{{% /notice %}}

When creating a new service, it comes with a set of access rules. These control who should have access to
the various parts of the service. The setup that comes with the service is a setup that will work for the vast majority
of simple services. _However, it is still important to consider what roles an end user must have to be able to
use the service_.

{{% insert "content/altinn-studio/v8/_includes/reference/default-altinn-roles.md" %}}

To only test a simple form in the test environment, no changes need to be made here. However, we still recommend making
a conscious choice here before the service is eventually put into production, and possibly removing the role that is not applicable to your service.
For example, if the service
is intended for use by private individuals, the "Director" role can be removed. If the service is to be submitted on behalf of a company, the
"Private individual" role can be removed.

If other roles are also relevant, these can also be added. A full overview of available roles in Altinn
[can be found here](https://info.altinn.no/hjelp/profil/alle-altinn-roller/).

The set of access rules comes with 2 rules:
- The first rule covers end users, and what access you want to give to end users with specific roles.
- The second rule covers the service owner, and what access you want to give to the service owner.

It will mostly be the rule covering end users that it will be relevant to change here.

For example, to remove the "Managing director (DAGL)" role:

1. Click on the "Settings" button in the top menu bar on the service workspace page.
2. Choose the "Access rules" tab from the left menu in "Settings".
3. Scroll down to the content of "Rule 1"
   - Find the field "Who should have these rights?"
4. In the field "Who should have these rights?", uncheck "Managing director"(/"Daglig leder") to remove it.
5. Optionally, add other roles from the dropdown list if needed.
6. The change is automatically saved when it is made. The "Settings" window can be closed.

<video autoplay loop controls muted src="./policy-rules.mp4">Your browser does not support video playback.</video>

{{%/expandlarge%}}

{{% expandlarge id="push-changes" header="Saving changes" %}}
{{% insert "content/altinn-studio/v8/_includes/concepts/local-vs-central-file-area.md" %}}

This is done by clicking on "Upload your changes" to the right in the top menu bar.

{{% insert "content/altinn-studio/v8/_includes/ui-patterns/upload-changes.md" %}}

<video autoplay loop controls muted src="./save-changes.mp4">Your browser does not support video playback.</video>

{{% insert "content/altinn-studio/v8/_includes/ui-patterns/fetch-changes.md" %}} 

{{% notice warning %}}
**Note!** If changes are made both in Altinn Studio and directly in the files of the service, conflicts may occur,
as the tool does not know which of the changes is applicable.

<br/>
It is therefore very wise to upload changes from Altinn Studio frequently, and if changes are made in the files directly,
you should always click "Fetch changes" before continuing to work on the service in Altinn Studio to avoid conflicts.
{{% /notice %}}

### Deleting "local" changes
{{% insert "content/altinn-studio/v8/_includes/procedures/delete-local-changes.md" %}}

<video autoplay loop controls muted src="./reset-local-changes.mp4">Your browser does not support video playback.</video>
{{% /expandlarge %}}

{{% expandlarge id="publish-service" header="Publishing the service" %}}
{{% notice info %}}
This section is only relevant if you have created a service for an _organization_. If you have created a test service for yourself,
you do not have access to any test environment, and the "Publish" button will not appear.
{{% /notice %}}

Publishing the service to the test and production environments is done via the "Publish" page. You can access this by clicking
the "Publish" button at the top right.

On the publishing page, you get an overview of all available environments, as well as the status of the service in each individual environment.

{{% insert "content/altinn-studio/v8/_includes/concepts/build-vs-publish.md" %}}

### Building a version
In the right column, enter the desired version name/number. {{% insert "content/altinn-studio/v8/_includes/procedures/naming-constraints-version.md" %}}

You can also provide a description of the version.

Click "Build version" to start the build, and wait for it to complete. This may take some time.

<video autoplay loop controls muted src="./build-version.mp4">Your browser does not support video playback.</video>


### Publishing a version
Once a version is built, it can be published to the desired environment. This is done by selecting the desired version from
the dropdown list associated with that environment. Then click "Publish new version" and confirm that you want to publish
the service to the environment.

The publication is then started, which may take some time. The status will be updated as soon as the service is available in the environment.

<video autoplay loop controls muted src="./publish-version.mp4">Your browser does not support video playback.</video>

{{%/expandlarge%}}
