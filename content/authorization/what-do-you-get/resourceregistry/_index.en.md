---
title: Resource Registry
linktitle: Resource Registry
description: The resource registry contains information about resources where Altinn Authorization is used for access management and control.
tags: [architecture, security, authorization, xacml, needstranslation]
---

{{<notice warning>}}
This is work in progress
{{</notice>}}

## Type of resources

There are different types of resources that can be registrated

- GenericAccessResource
- MaskinportenSchema
- Systemresource

Later it will be possible to registrate

- Altinn 3 Apps
- Legacy Altinn 2 services for legacy archive authorization (not finalized)

### Generic Access Resources

GenericAccessResources will be used as linkServices are used in Altinn 2.

The resource would be any type of service provided by public organiazations.

We used [cpsv:PublicService](https://informasjonsforvaltning.github.io/cpsv-ap-no/#OffentligTjeneste) as inspiration to the data model.

This also allows Felles datakatalog to consume the definition for their [service catalogue](https://data.norge.no/public-services-and-events)

See full list [in production](https://platform.altinn.no/resourceregistry/api/v1/resource/search).

Some examples

- API's exposing data [Example3](exampleresource3.json) [XACML](policysample3.xml)
- Portal functionality in Altinn [Example 1](exampleresource1.json) [XACML](policysample3.xml)
- Portal functionality in external portal [Example 2](exampleresource2.json)
- Samordna registermelding [Example 4](exampleresource4.json) [XACML](policysample4.xml)
- Avtale om Arbeidstrening [Example 6](exampleresource6.json) [XACML](policysample6.xml)
- Lakselus MaskinPortenSchema [Example 7](https://platform.altinn.no/resourceregistry/api/v1/resource/mat-maskinportenschema-lakselusrapportering/) [XACML](https://platform.altinn.no/resourceregistry/api/v1/resource/mat-maskinportenschema-lakselusrapportering/policy)

## Resource attributes

The below table lists the attributes a resource has in the resource registry. For attributes defined in cpsv:PublicService there is a link to the description.

{{% insert "content/shared/authorization/tables/resource-attributes.en.md" %}}

## Policies

Polices defined for apps and resources will be stored by resource registry.

### App Policies

The App Policies are policies for Apps [created in Altinn Studio](/en/altinn-studio/v8/reference/configuration/authorization/).
The policy is created in Altinn Studio and migrated to the Access Policy component when the app is deployed to a test or production environment.

An app policy contains information about the different resources in an App and who and what kind of operations they are allowed to perform.
The who is identified using Altinn Roles, Access Groups, or roles/groups from other sources.

**Example**

- [BRG RRH-Innrapportering](apppolicy_brg_rrh-innrapportering.xml)

### Resource Registry Policies

The resource registry policies are policies for resources that is not comming from Altinn 3 apps. It could be any functionality hosted on any platform.

Both digital and analog services can be registrated in the resource registry.

### Administration from Altinn Studio

![Resource Admin](resourceadmin1.png "Resource Admin in Altinn Studio")

![Resource Admin](resourceadmin2.png "Resource Admin in Altinn Studio")

![Resource Admin](resourceadmin3.png "Resource Admin in Altinn Studio")

## Construction

See [construction components](/en/authorization/reference/architecture/resourceregistry/) if you want to see how the component is built.
