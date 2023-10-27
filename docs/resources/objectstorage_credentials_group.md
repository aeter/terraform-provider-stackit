---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "stackit_objectstorage_credentials_group Resource - stackit"
subcategory: ""
description: |-
  ObjectStorage credentials group resource schema. Must have a region specified in the provider configuration.
---

# stackit_objectstorage_credentials_group (Resource)

ObjectStorage credentials group resource schema. Must have a `region` specified in the provider configuration.

## Example Usage

```terraform
resource "stackit_objectstorage_credentials_group" "example" {
  project_id = "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
  name       = "example-credentials-group"
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `name` (String) The credentials group's display name.
- `project_id` (String) Project ID to which the credentials group is associated.

### Read-Only

- `credentials_group_id` (String) The credentials group ID
- `id` (String) Terraform's internal data source identifier. It is structured as "`project_id`,`credentials_group_id`".
- `urn` (String) Credentials group uniform resource name (URN)