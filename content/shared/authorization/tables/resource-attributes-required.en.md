| Attribute             | Description                                                                                                                                             |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| identifier            | Globally unique ID for the resource. Also used in policy. Required.                                                                                     |
| title                 | Title for the resource. Displayed in the Altinn portal. Must be provided for en, nb, and nn (English, Bokmål, and Nynorsk). Required. |
| description           | Description for the resource. Must be provided for en, nb, and nn (English, Bokmål, and Nynorsk). Required.                                           |
| rightDescription      | Describes the power of attorney given in access management. Must be provided for en, nb, and nn (English, Bokmål, and Nynorsk). Required if delegable is true. |
| resourceReferences    | Reference to other IDs or values. For MaskinportenSchema resources, a reference with type MaskinportenScope must be added. |
| hasCompetentAuthority | Defines the service owner. Must be set with the organization number and correct service owner code (NAV, SKD, SVV, etc.).                               |
| contactpoint | Who to contact about the service |
| limitedByRRR                                                                                                        | Defines if RRR will be used to controll access                     |
| availableForType                                                                                                    | Defines what type of party that can use service                    |
| selfIdentifiedUserEnabled                                                                                          | The user acting on behalf of party can be a selfidentifed users    |
| enterpriseUserEnabled                                                                                              | The user acting on behalf of party can be an enterprise users      |
| resourceType                                                                                                        | Type of resource. Must be set to MaskinportenSchema for API schemes, GenericAccessResource for generic resources, or Systemresource for system resources.                                                  |
| delegable                                                                                                           | Indicates if a rights to performe a service can be given to others. Must be set to true for delegable resources. |
| visible                                                                                                             | Indicates if a service should be visible to users in GUI. Must be set to true for delegable resources.            |