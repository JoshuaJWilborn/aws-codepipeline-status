# aws-codepipeline-status
Various bash utilities and scripts to keep track of aws code pipeline statuses (passing, failing, building etc)

Requirements:

* aws credentials properly configured in ~/.aws/credentials and ~/.aws/config
* jq package
* json configuration file

Schema for JSON config file:
```json
{
  "definitions": {},
  "$schema": "http://json-schema.org/draft-07/schema#",
  "$id": "http://example.com/root.json",
  "type": "object",
  "title": "The Root Schema",
  "required": [
    "services"
  ],
  "properties": {
    "services": {
      "$id": "#/properties/services",
      "type": "array",
      "title": "The Services Schema",
      "items": {
        "$id": "#/properties/services/items",
        "type": "object",
        "title": "The Items Schema",
        "required": [
          "name",
          "region",
          "profile",
          "stage"
        ],
        "properties": {
          "name": {
            "$id": "#/properties/services/items/properties/name",
            "type": "string",
            "title": "The Name Schema",
            "default": "",
            "examples": [
              "aws-adapter"
            ],
            "pattern": "^(.*)$"
          },
          "region": {
            "$id": "#/properties/services/items/properties/region",
            "type": "string",
            "title": "The Region Schema",
            "default": "",
            "examples": [
              "us-east-1"
            ],
            "pattern": "^(.*)$"
          },
          "profile": {
            "$id": "#/properties/services/items/properties/profile",
            "type": "string",
            "title": "The Profile Schema",
            "default": "",
            "examples": [
              "eng-tooling"
            ],
            "pattern": "^(.*)$"
          },
          "stage": {
            "$id": "#/properties/services/items/properties/stage",
            "type": "string",
            "title": "The Stage Schema",
            "default": "",
            "examples": [
              "Development"
            ],
            "pattern": "^(.*)$"
          }
        }
      }
    }
  }
}
```


