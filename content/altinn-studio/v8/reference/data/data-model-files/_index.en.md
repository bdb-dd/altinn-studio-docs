---
title: Data Model Files
description: Reference for data model file types, formats, and storage locations
weight: 1
toc: true
---

## Overview

Altinn Studio uses multiple file formats to represent data models. Each format serves a specific purpose in the application lifecycle.

## Application Data Model Files

Data models for applications are stored in the application repository under `App/models/`.

{{% insert "content/altinn-studio/v8/_includes/reference/data-model-file-types.md" %}}

## Organization Data Model Repository

### Repository Structure

Organization data models are stored in a dedicated repository: `<org>-datamodels`

**Repository location:** `https://altinn.studio/repos/<org>/<org>-datamodels`

**Example:** The Test Department (ttd) data models are at:
`https://altinn.studio/repos/ttd/ttd-datamodels`

### Access Permissions

**View access:** Public by default (anyone can view)
**Edit access:** Requires membership in the organization's _Data models_ team

See [access management](/en/altinn-studio/v8/guides/administration/access-management/studio/) for details on managing team membership.

### File Organization

Data models can be organized in folders within the `<org>-datamodels` repository. There are no restrictions on folder structure.

## File Generation Flow

```
XSD Upload → JSON Schema → C# Model
                ↓
           JSON Metadata (temporary)
```

1. Upload an XSD file to Altinn Studio
2. Tool generates JSON Schema file
3. Edit the JSON Schema in the tool (changes auto-save)
4. Click "Generate Models" to create XSD and C# files

## Model Selection in Altinn Studio

{{% insert "content/altinn-studio/v8/_includes/concepts/data-model-dropdown-categories.md" %}}

## Related Documentation

- [Working with Data Models (How-To)](/en/altinn-studio/v8/guides/development/data-modeling/)
- [Altinn 2 Data Model Migration](/en/altinn-studio/v8/guides/altinn-2/altinn-2-datamodel/)
- [Seres Migration Guide](/en/altinn-studio/v8/guides/altinn-2/seres-migration/)