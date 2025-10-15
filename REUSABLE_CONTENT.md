# Reusable Content Components

This document describes the reusable content components available in the documentation.

## Maskinporten Prerequisites

### Usage

Use the `insert` shortcode to include prerequisite lists for different Maskinporten setup scenarios.

```markdown
{{% insert "content/shared/authorization/prerequisites/api-scheme.en.md" %}}
```

### Available Files

- `api-provider.en.md` - Prerequisites for API providers creating resources
- `api-scheme.en.md` - Prerequisites for creating delegable API schemes
- `system-vendor.en.md` - Prerequisites for system vendors
- `consent.en.md` - Prerequisites for consent resources
- `resource-admin.en.md` - Generic resource registry access prerequisites

### Example

```markdown
## Prerequisites

{{% insert "content/shared/authorization/prerequisites/system-vendor.en.md" %}}
```

### Content Source

Content files are stored in: `content/shared/authorization/prerequisites/`

To add or modify prerequisite lists, edit the appropriate markdown file.

## Resource Attributes Tables

### Usage

Use the `insert` shortcode to include resource registry attributes tables. There are three versions available:

**Full table (all attributes with details):**
```markdown
{{% insert "content/shared/authorization/tables/resource-attributes.en.md" %}}
```

**Required attributes only (simplified for guides):**
```markdown
{{% insert "content/shared/authorization/tables/resource-attributes-required.en.md" %}}
```

**Optional attributes:**
```markdown
{{% insert "content/shared/authorization/tables/resource-attributes-optional.en.md" %}}
```

### Example

```markdown
## Resource attributes

The following attributes are necessary:

{{% insert "content/shared/authorization/tables/resource-attributes-required.en.md" %}}
```

### Content Source

Content is stored in: `content/shared/authorization/tables/`

Available files:
- `resource-attributes.en.md` - Complete table with all attributes
- `resource-attributes-required.en.md` - Required attributes only (focused for API scheme guides)
- `resource-attributes-optional.en.md` - Optional attributes with full details

These are standard markdown tables. To add or modify resource attributes, edit the appropriate file.

## Benefits of Reusable Content

1. **Consistency** - Same information displayed identically across all pages
2. **Maintainability** - Update once in the data file, reflects everywhere
3. **Accuracy** - Single source of truth reduces errors
4. **Translation** - Easier to manage translations
5. **Updates** - When APIs or requirements change, update in one place

## Files Structure

```
altinn-studio-docs/
└── content/
    └── shared/
        └── authorization/
            ├── prerequisites/
            │   ├── api-provider.en.md
            │   ├── api-scheme.en.md
            │   ├── system-vendor.en.md
            │   ├── consent.en.md
            │   └── resource-admin.en.md
            └── tables/
                ├── resource-attributes.en.md
                ├── resource-attributes-required.en.md
                └── resource-attributes-optional.en.md
```

## Migration Guide

### Replacing Inline Prerequisites

**Before:**
```markdown
## Prerequisites

- The organization must have a client in Maskinporten.
- The organization must have received the scopes `altinn:resourceregistry/resource.write` and `altinn:resourceregistry/resource.read`.
- The organization must have received the scope `altinn:maskinporten/delegationschemes.write`.
- The organization must have created a Maskinporten client configured with these scopes.
```

**After:**
```markdown
## Prerequisites

{{% insert "content/shared/authorization/prerequisites/api-scheme.en.md" %}}
```

### Replacing Resource Attributes Tables

**Before:**
```markdown
| Attribute | Description | Used for i Altinn | Format | Mand. |
| --------- | ----------- | ----------------- | ------ | ----- |
| identifier | Identifies the resource. | Altinn tjenestekatalog + Tilgangsstyring + Tilgangskontroll. | Unik og persistent. Fritekst, max ? tegn. Bør være lesbar. | Yes |
| title | The resource title | Altinn tjenestekatalog + Tilgangsstyring. (search) | Fritekst, max ? tegn, på alle språk (nb, nn, en) | Yes |
...
```

**After:**
```markdown
{{% insert "content/shared/authorization/tables/resource-attributes.en.md" %}}
```

## Next Steps

Consider implementing similar reusable components for:

1. JWT Token Examples (system user, consent tokens)
2. API Endpoint References
3. External Documentation Links
4. XACML Policy Structure
5. PDP Authorization Examples
6. Common Terminology/Glossary Terms