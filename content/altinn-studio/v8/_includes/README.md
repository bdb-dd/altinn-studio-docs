# Atomic Content Components

This directory contains reusable content components extracted from the Altinn Studio documentation using atomic content principles.

## Directory Structure

- **`concepts/`** - Conceptual explanations that can be reused across how-to guides and reference docs
- **`procedures/`** - Common procedures and constraints
- **`reference/`** - Reference information (lists, categories, etc.)
- **`ui-patterns/`** - UI interaction patterns that are repeated across guides

## Usage

Include these files in your documentation using the `insert` shortcode:

```markdown
{{% insert "content/altinn-studio/v8/_includes/concepts/data-model-definition.md" %}}
```

## Available Components

### Concepts
- `data-model-definition.md` - Explanation of what a data model is
- `service-name-vs-display-name.md` - Difference between service name and display name
- `local-vs-central-file-area.md` - Explanation of local vs central file areas
- `build-vs-publish.md` - Two-step publishing process explanation
- `data-model-dropdown-categories.md` - Explanation of XSD vs JSON Schema categories in dropdown

### UI Patterns
- `bind-component-to-data-model.md` - How to bind form components to data model fields
- `add-text-to-component.md` - How to add texts (heading, description, help) to components
- `upload-changes.md` - How to upload changes to central file area
- `fetch-changes.md` - How to fetch changes from central file area

### Procedures
- `naming-constraints-service.md` - Service name constraints
- `naming-constraints-version.md` - Version name constraints
- `delete-local-changes.md` - Procedure to delete local changes
- `navigate-to-data-modeling-tool.md` - Steps to access the Data Modeling tool

### Reference
- `form-component-categories.md` - List of form component categories (Standard, Text, Advanced)
- `default-altinn-roles.md` - Default Altinn roles in service templates
- `data-model-file-types.md` - Description of the four data model file types (C#, JSON Schema, XSD, JSON metadata)

## Maintenance

When updating these components:
1. Consider which pages will be affected by the change
2. Test the build after making changes
3. Verify content renders correctly in context

## Examples

### basic-form Guide
The `guides/development/basic-form/_index.en.md` guide has been decomposed to use these atomic components, demonstrating how they can be reused while maintaining readability.

### Data Modeling Documentation
The original `reference/data/data-modeling/_index.en.md` has been refactored following Diátaxis principles:
- **How-To Guide:** `guides/development/data-modeling/_index.en.md` - Task-oriented instructions
- **Reference:** `reference/data/data-model-files/_index.en.md` - Technical specifications

Both documents use atomic components for consistent messaging across documentation types.