---
subcategory: "App Service (Web Apps)"
layout: "azurerm"
page_title: "Azure Resource Manager: azurerm_source_control_token"
description: |-
  Manages an App Service GitHub Token.
---

# azurerm_source_control_token

Manages an App Service Source Control Token.

~> **NOTE:** This resource can only manage the token for the user currently running Terraform. Managing tokens for another user is not supported by the service. 

~> **NOTE:** This is a 3.0 Beta resource, please see the [3.0 Beta guide](https://github.com/hashicorp/terraform-provider-azurerm/blob/f/main/website/docs/guides/3.0-beta.html.markdown) for more information on enabling and using this resource.

## Example Usage

```hcl
resource "azurerm_source_control_token" "example" {
  type  = "GitHub"
  token = "ghp_sometokenvaluesecretsauce"
}
```

## Arguments Reference

The following arguments are supported:

* `type` - (Required) The Token type. Possible values include `Bitbucket`, `Dropbox`, `Github`, and `OneDrive`.

* `token` - (Required) The Access Token.

~> **NOTE:** The token used for deploying App Service needs the following permissions: `repo` and `workflow`.

## Attributes Reference

In addition to the Arguments listed above - the following Attributes are exported: 

* `id` - The ID of the App Service Source GitHub Token.

## Timeouts

The `timeouts` block allows you to specify [timeouts](https://www.terraform.io/docs/configuration/resources.html#timeouts) for certain actions:

* `create` - (Defaults to 5 minutes) Used when creating the App Service Source GitHub Token.
* `read` - (Defaults to 5 minutes) Used when retrieving the App Service Source GitHub Token.
* `update` - (Defaults to 5 minutes) Used when updating the App Service Source GitHub Token.
* `delete` - (Defaults to 5 minutes) Used when deleting the App Service Source GitHub Token.

## Import

App Service Source Github Tokens can be imported using the `resource id`, e.g.

```shell
terraform import azurerm_app_service_github_token.example /providers/Microsoft.Web/sourcecontrols/GitHub
```