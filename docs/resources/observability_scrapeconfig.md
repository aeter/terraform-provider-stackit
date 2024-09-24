---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "stackit_observability_scrapeconfig Resource - stackit"
subcategory: ""
description: |-
  Observability scrape config resource schema. Must have a region specified in the provider configuration.
---

# stackit_observability_scrapeconfig (Resource)

Observability scrape config resource schema. Must have a `region` specified in the provider configuration.

## Example Usage

```terraform
resource "stackit_observability_scrapeconfig" "example" {
  project_id   = "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
  instance_id  = "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
  name         = "example-job"
  metrics_path = "/my-metrics"
  saml2 = {
    enable_url_parameters = true
  }
  targets = [
    {
      urls = ["url1", "urls2"]
      labels = {
        "url1" = "dev"
      }
    }
  ]
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `instance_id` (String) Observability instance ID to which the scraping job is associated.
- `metrics_path` (String) Specifies the job scraping url path. E.g. `/metrics`.
- `name` (String) Specifies the name of the scraping job.
- `project_id` (String) STACKIT project ID to which the scraping job is associated.
- `targets` (Attributes List) The targets list (specified by the static config). (see [below for nested schema](#nestedatt--targets))

### Optional

- `basic_auth` (Attributes) A basic authentication block. (see [below for nested schema](#nestedatt--basic_auth))
- `saml2` (Attributes) A SAML2 configuration block. (see [below for nested schema](#nestedatt--saml2))
- `sample_limit` (Number) Specifies the scrape sample limit. Upper limit depends on the service plan. Defaults to `5000`.
- `scheme` (String) Specifies the http scheme. Defaults to `https`.
- `scrape_interval` (String) Specifies the scrape interval as duration string. Defaults to `5m`.
- `scrape_timeout` (String) Specifies the scrape timeout as duration string. Defaults to `2m`.

### Read-Only

- `id` (String) Terraform's internal resource ID. It is structured as "`project_id`,`instance_id`,`name`".

<a id="nestedatt--targets"></a>
### Nested Schema for `targets`

Required:

- `urls` (List of String) Specifies target URLs.

Optional:

- `labels` (Map of String) Specifies labels.


<a id="nestedatt--basic_auth"></a>
### Nested Schema for `basic_auth`

Required:

- `password` (String, Sensitive) Specifies basic auth password.
- `username` (String) Specifies basic auth username.


<a id="nestedatt--saml2"></a>
### Nested Schema for `saml2`

Optional:

- `enable_url_parameters` (Boolean) Specifies if URL parameters are enabled. Defaults to `true`