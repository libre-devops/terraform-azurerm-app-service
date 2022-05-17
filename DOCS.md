## Requirements

No requirements.

## Providers

| Name | Version |
|------|---------|
| <a name="provider_azurerm"></a> [azurerm](#provider\_azurerm) | n/a |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [azurerm_app_service_virtual_network_swift_connection.function_vnet_integration](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/app_service_virtual_network_swift_connection) | resource |
| [azurerm_function_app.function_app](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/function_app) | resource |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_active_directory_auth_setttings"></a> [active\_directory\_auth\_setttings](#input\_active\_directory\_auth\_setttings) | Acitve directory authentication provider settings for app service | `any` | `{}` | no |
| <a name="input_app_amount"></a> [app\_amount](#input\_app\_amount) | The amount of apps to be created | `number` | n/a | yes |
| <a name="input_app_name"></a> [app\_name](#input\_app\_name) | The name of the function app | `string` | n/a | yes |
| <a name="input_app_service_plan_id"></a> [app\_service\_plan\_id](#input\_app\_service\_plan\_id) | Id of the App Service Plan for Function App hosting | `string` | n/a | yes |
| <a name="input_application_insights_enabled"></a> [application\_insights\_enabled](#input\_application\_insights\_enabled) | Enable or disable the Application Insights deployment | `bool` | `true` | no |
| <a name="input_application_insights_id"></a> [application\_insights\_id](#input\_application\_insights\_id) | ID of the existing Application Insights to use instead of deploying a new one. | `string` | `null` | no |
| <a name="input_application_insights_type"></a> [application\_insights\_type](#input\_application\_insights\_type) | Application Insights type if need to be generated | `string` | `"web"` | no |
| <a name="input_application_zip_package_path"></a> [application\_zip\_package\_path](#input\_application\_zip\_package\_path) | Local or remote path of a zip package to deploy on the Function App | `string` | `null` | no |
| <a name="input_authorized_ips"></a> [authorized\_ips](#input\_authorized\_ips) | IPs restriction for Function. See documentation https://www.terraform.io/docs/providers/azurerm/r/function_app.html#ip_restriction | `list(string)` | `[]` | no |
| <a name="input_authorized_subnet_ids"></a> [authorized\_subnet\_ids](#input\_authorized\_subnet\_ids) | Subnets restriction for Function. See documentation https://www.terraform.io/docs/providers/azurerm/r/function_app.html#ip_restriction | `list(string)` | `[]` | no |
| <a name="input_backup_settings"></a> [backup\_settings](#input\_backup\_settings) | Backup settings for App service | <pre>object({<br>    name                     = string<br>    enabled                  = bool<br>    storage_account_url      = optional(string)<br>    frequency_interval       = number<br>    frequency_unit           = optional(string)<br>    retention_period_in_days = optional(number)<br>    start_time               = optional(string)<br>  })</pre> | <pre>{<br>  "enabled": false,<br>  "frequency_interval": 1,<br>  "frequency_unit": "Day",<br>  "name": "DefaultBackup",<br>  "retention_period_in_days": 1<br>}</pre> | no |
| <a name="input_connection_strings"></a> [connection\_strings](#input\_connection\_strings) | Connection strings for App Service | `list(map(string))` | `[]` | no |
| <a name="input_custom_domains"></a> [custom\_domains](#input\_custom\_domains) | Custom domains with SSL binding and SSL certificates for the App Service. Getting the SSL certificate from an Azure Keyvault Certificate Secret or a file is possible. | `map(map(string))` | `null` | no |
| <a name="input_default_auth_provider"></a> [default\_auth\_provider](#input\_default\_auth\_provider) | The default provider to use when multiple providers have been set up. Possible values are `AzureActiveDirectory`, `Facebook`, `Google`, `MicrosoftAccount` and `Twitter` | `string` | `"AzureActiveDirectory"` | no |
| <a name="input_disable_ip_masking"></a> [disable\_ip\_masking](#input\_disable\_ip\_masking) | By default the real client ip is masked as `0.0.0.0` in the logs. Use this argument to disable masking and log the real client ip | `bool` | `false` | no |
| <a name="input_enable_auth_settings"></a> [enable\_auth\_settings](#input\_enable\_auth\_settings) | Specifies the Authenication enabled or not | `bool` | `false` | no |
| <a name="input_enable_backup"></a> [enable\_backup](#input\_enable\_backup) | bool to to setup backup for app service | `bool` | `false` | no |
| <a name="input_enable_client_affinity"></a> [enable\_client\_affinity](#input\_enable\_client\_affinity) | Should the App Service send session affinity cookies, which route client requests in the same session to the same instance? | `bool` | `false` | no |
| <a name="input_enable_client_certificate"></a> [enable\_client\_certificate](#input\_enable\_client\_certificate) | Does the App Service require client certificates for incoming requests | `bool` | `false` | no |
| <a name="input_enable_https"></a> [enable\_https](#input\_enable\_https) | Can the App Service only be accessed via HTTPS? | `bool` | `false` | no |
| <a name="input_environment"></a> [environment](#input\_environment) | Project environment | `string` | n/a | yes |
| <a name="input_function_app_application_settings"></a> [function\_app\_application\_settings](#input\_function\_app\_application\_settings) | Function App application settings | `map(string)` | `{}` | no |
| <a name="input_function_app_version"></a> [function\_app\_version](#input\_function\_app\_version) | Version of the function app runtime to use (Allowed values 2 or 3) | `number` | `3` | no |
| <a name="input_function_app_vnet_integration_enabled"></a> [function\_app\_vnet\_integration\_enabled](#input\_function\_app\_vnet\_integration\_enabled) | Enable VNET integration with the Function App. `function_app_vnet_integration_subnet_id` is mandatory if enabled | `bool` | `false` | no |
| <a name="input_function_app_vnet_integration_subnet_id"></a> [function\_app\_vnet\_integration\_subnet\_id](#input\_function\_app\_vnet\_integration\_subnet\_id) | ID of the subnet to associate with the Function App (VNet integration) | `string` | `null` | no |
| <a name="input_function_language_for_linux"></a> [function\_language\_for\_linux](#input\_function\_language\_for\_linux) | Language of the Function App on Linux hosting, can be "dotnet", "node" or "python" | `string` | `"dotnet"` | no |
| <a name="input_https_only"></a> [https\_only](#input\_https\_only) | Disable http procotol and keep only https | `bool` | `true` | no |
| <a name="input_identity_ids"></a> [identity\_ids](#input\_identity\_ids) | UserAssigned Identities ID to add to Function App. Mandatory if type is UserAssigned | `list(string)` | `null` | no |
| <a name="input_identity_type"></a> [identity\_type](#input\_identity\_type) | Add an Identity (MSI) to the function app. Possible values are SystemAssigned or UserAssigned | `string` | `"SystemAssigned"` | no |
| <a name="input_ip_restriction_headers"></a> [ip\_restriction\_headers](#input\_ip\_restriction\_headers) | IPs restriction headers for Function. See documentation https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/function_app#headers | `map(list(string))` | `null` | no |
| <a name="input_location"></a> [location](#input\_location) | Azure location. | `string` | n/a | yes |
| <a name="input_location_short"></a> [location\_short](#input\_location\_short) | Short string for Azure location. | `string` | n/a | yes |
| <a name="input_os_type"></a> [os\_type](#input\_os\_type) | A string indicating the Operating System type for this function app. | `string` | `null` | no |
| <a name="input_password_end_date"></a> [password\_end\_date](#input\_password\_end\_date) | The relative duration or RFC3339 rotation timestamp after which the password expire | `any` | `null` | no |
| <a name="input_password_rotation_in_years"></a> [password\_rotation\_in\_years](#input\_password\_rotation\_in\_years) | Number of years to add to the base timestamp to configure the password rotation timestamp. Conflicts with password\_end\_date and either one is specified and not the both | `number` | `2` | no |
| <a name="input_retention_in_days"></a> [retention\_in\_days](#input\_retention\_in\_days) | Specifies the retention period in days. Possible values are `30`, `60`, `90`, `120`, `180`, `270`, `365`, `550` or `730` | `number` | `90` | no |
| <a name="input_rg_name"></a> [rg\_name](#input\_rg\_name) | Resource group name | `string` | n/a | yes |
| <a name="input_scm_authorized_ips"></a> [scm\_authorized\_ips](#input\_scm\_authorized\_ips) | SCM IPs restriction for Function. See documentation https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/function_app#scm_ip_restriction | `list(string)` | `[]` | no |
| <a name="input_scm_authorized_subnet_ids"></a> [scm\_authorized\_subnet\_ids](#input\_scm\_authorized\_subnet\_ids) | SCM subnets restriction for Function. See documentation https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/function_app#scm_ip_restriction | `list(string)` | `[]` | no |
| <a name="input_scm_cidrs"></a> [scm\_cidrs](#input\_scm\_cidrs) | CIDRs for SCM | `list(string)` | n/a | yes |
| <a name="input_scm_ip_restriction_headers"></a> [scm\_ip\_restriction\_headers](#input\_scm\_ip\_restriction\_headers) | IPs restriction headers for Function. See documentation https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/function_app#scm_ip_restriction | `map(list(string))` | `null` | no |
| <a name="input_scm_service_tags"></a> [scm\_service\_tags](#input\_scm\_service\_tags) | Service tags for SCM | `list(string)` | n/a | yes |
| <a name="input_scm_subnets"></a> [scm\_subnets](#input\_scm\_subnets) | Subnets for SCM | `list(string)` | n/a | yes |
| <a name="input_site_config"></a> [site\_config](#input\_site\_config) | Site config for App Service. See documentation https://www.terraform.io/docs/providers/azurerm/r/app_service.html#site_config. IP restriction attribute is not managed in this block. | `any` | `{}` | no |
| <a name="input_storage_account_access_key"></a> [storage\_account\_access\_key](#input\_storage\_account\_access\_key) | Access key the storage account to use. If null a new storage account is created | `string` | `null` | no |
| <a name="input_storage_account_enable_advanced_threat_protection"></a> [storage\_account\_enable\_advanced\_threat\_protection](#input\_storage\_account\_enable\_advanced\_threat\_protection) | Boolean flag which controls if advanced threat protection is enabled, see [here](https://docs.microsoft.com/en-us/azure/storage/common/storage-advanced-threat-protection?tabs=azure-portal) for more information. | `bool` | `false` | no |
| <a name="input_storage_account_enable_https_traffic_only"></a> [storage\_account\_enable\_https\_traffic\_only](#input\_storage\_account\_enable\_https\_traffic\_only) | Boolean flag which controls if https traffic only is enabled. | `bool` | `true` | no |
| <a name="input_storage_account_kind"></a> [storage\_account\_kind](#input\_storage\_account\_kind) | Storage Account Kind | `string` | `"StorageV2"` | no |
| <a name="input_storage_account_min_tls_version"></a> [storage\_account\_min\_tls\_version](#input\_storage\_account\_min\_tls\_version) | Storage Account minimal TLS version | `string` | `"TLS1_2"` | no |
| <a name="input_storage_account_name"></a> [storage\_account\_name](#input\_storage\_account\_name) | Name of storage account | `string` | n/a | yes |
| <a name="input_storage_container_name"></a> [storage\_container\_name](#input\_storage\_container\_name) | The name of the storage container to keep backups | `any` | `null` | no |
| <a name="input_storage_mounts"></a> [storage\_mounts](#input\_storage\_mounts) | Storage account mount points for App Service | `list(map(string))` | `[]` | no |
| <a name="input_tags"></a> [tags](#input\_tags) | A map of the tags to use on the resources that are deployed with this module. | `map(string)` | <pre>{<br>  "source": "terraform"<br>}</pre> | no |
| <a name="input_token_store_enabled"></a> [token\_store\_enabled](#input\_token\_store\_enabled) | If enabled the module will durably store platform-specific security tokens that are obtained during login flows | `bool` | `false` | no |
| <a name="input_unauthenticated_client_action"></a> [unauthenticated\_client\_action](#input\_unauthenticated\_client\_action) | The action to take when an unauthenticated client attempts to access the app. Possible values are `AllowAnonymous` and `RedirectToLoginPage` | `string` | `"RedirectToLoginPage"` | no |

## Outputs

No outputs.
