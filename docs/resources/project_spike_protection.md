---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "sentry_project_spike_protection Resource - terraform-provider-sentry"
subcategory: ""
description: |-
  Sentry Project Spike Protection resource. This resource is used to create and manage spike protection for a project.
---

# sentry_project_spike_protection (Resource)

Sentry Project Spike Protection resource. This resource is used to create and manage spike protection for a project.

## Example Usage

```terraform
resource "sentry_project" "default" {
  organization = "my-organization"

  teams = ["my-first-team", "my-second-team"]
  name  = "web-app"

  platform = "javascript"
}

# Enable spike protection for the project
resource "sentry_project_spike_protection" "default" {
  organization = sentry_project.default.organization
  project      = sentry_project.default.id
  enabled      = true
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `enabled` (Boolean) Toggle the browser-extensions, localhost, filtered-transaction, or web-crawlers filter on or off.
- `organization` (String) The slug of the organization the project belongs to.
- `project` (String) The slug of the project to create the filter for.

### Read-Only

- `id` (String) The ID of this resource.