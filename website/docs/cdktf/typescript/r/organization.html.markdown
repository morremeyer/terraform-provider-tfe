---
layout: "tfe"
page_title: "Terraform Enterprise: tfe_organization"
description: |-
  Manages organizations.
---

# tfe_organization

Manages organizations.

## Example Usage

Basic usage:

```typescript
import * as constructs from "constructs";
import * as cdktf from "cdktf";
/*Provider bindings are generated by running cdktf get.
See https://cdk.tf/provider-generation for more details.*/
import * as tfe from "./.gen/providers/tfe";
class MyConvertedCode extends cdktf.TerraformStack {
  constructor(scope: constructs.Construct, name: string) {
    super(scope, name);
    new tfe.organization.Organization(this, "test", {
      email: "admin@company.com",
      name: "my-org-name",
    });
  }
}

```

## Argument Reference

The following arguments are supported:

* `name` - (Required) Name of the organization.
* `email` - (Required) Admin email address.
* `sessionTimeoutMinutes` - (Optional) Session timeout after inactivity.
  Defaults to `20160`.
* `sessionRememberMinutes` - (Optional) Session expiration. Defaults to
  `20160`.
* `collaboratorAuthPolicy` - (Optional) Authentication policy (`password`
  or `twoFactorMandatory`). Defaults to `password`.
* `ownersTeamSamlRoleId` - (Optional) The name of the "owners" team.
* `costEstimationEnabled` - (Optional) Whether or not the cost estimation feature is enabled for all workspaces in the organization. Defaults to true. In a Terraform Cloud organization which does not have Teams & Governance features, this value is always false and cannot be changed. In Terraform Enterprise, Cost Estimation must also be enabled in Site Administration.
* `sendPassingStatusesForUntriggeredSpeculativePlans` - (Optional) Whether or not to send VCS status updates for untriggered speculative plans. This can be useful if large numbers of untriggered workspaces are exhausting request limits for connected version control service providers like GitHub. Defaults to false. In Terraform Enterprise, this setting has no effect and cannot be changed but is also available in Site Administration.
* `assessmentsEnforced` - (Optional) (Available only in Terraform Cloud) Whether to force health assessments (drift detection) on all eligible workspaces or allow workspaces to set their own preferences.
* `allowForceDeleteWorkspaces` - (Optional) Whether workspace administrators are permitted to delete workspaces with resources under management. If false, only organization owners may delete these workspaces. Defaults to false.

## Attributes Reference

* `id` - The name of the organization.

## Import

Organizations can be imported; use `<ORGANIZATION NAME>` as the import ID. For
example:

```shell
terraform import tfe_organization.test my-org-name
```

<!-- cache-key: cdktf-0.17.0-pre.15 input-e999dce0c812e7592cf4dee664b3d7cf3ca7d5544304b1163f915d3bcd134ee2 -->