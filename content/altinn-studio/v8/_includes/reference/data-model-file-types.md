Each data model consists of four files:

- **C# data model** (`<model>.cs`): Used by the application backend and APIs for data processing and validation on the server side.
- **JSON Schema** (`<model>.schema.json`): Used by the application frontend for real-time client-side data validation. This is the primary file edited in the Data Modeling tool.
- **XSD data model** (`<model>.xsd`): XML schema definition that defines valid XML document structure. Can be uploaded to generate other model files or downloaded for external use.
- **JSON metadata** (`<model>.metadata.json`): Internal metadata used by Altinn Studio to generate the C# file. This file is not stored in the application repository.