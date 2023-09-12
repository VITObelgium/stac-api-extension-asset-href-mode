# STAC API - asset-href-mode extension specification

## Overview
- **Title:** asset-href-mode
- **OpenAPI specification:** [openapi.yaml](openapi.yaml)
- **Conformance Classes:**
- **Scope:** STAC API - Features, STAC API - Item Search
- **[Extension Maturity Classification](https://github.com/radiantearth/stac-api-spec/tree/main/README.md#maturity-classification):** Proposal
- **Dependencies:**
  - STAC API - Item Search
  - STAC API - Features
- **Owner:** [@VITObelgium](https://github.com/VITObelgium)

The purpose of the asset-href-mode extension is to provide a way to handle different asset links for alternative data access methods. Depending on the selected data access method, the correct asset href links will be returned.

## Endpoints
The extensions adds endpoints to retrieve the different supported data access methods, both on the catalogue level and the collection level.
| Endpoint | Returns | Description |
| --- | --- | --- |
| `/asset-href-modes` | JSON | Retrieves all asset-href-modes supported by this catalogue.
| `/{collectionId}/asset-href-modes` | JSON | Retrieves asset-href-modes supported for this specific collection.

Example response for the `/asset-href-modes` endpoint:
```json
{
    "title": "asset-href-modes for STAC API",
    "description": "Supported values for the asset-href-mode parameter.",
    "properties": {
        "HTTP": {
            "description": "HTTP download link"
        },
        "S3": {
            "description": "AWS S3 path"
        }
    }
}
```

## Parameters
This extension adds the `asset-href-mode` parameter to the item search and features scope. Depending on the value of this parameter, the correct asset href links will be returned.