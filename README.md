# External DNS into AWS

![Tfsec](https://github.com/nlamirault/terraform-aws-external-dns/workflows/Tfsec/badge.svg)

## Usage

```hcl
module "external_dns" {
  source  = "nlamirault/external-dns/aws"
  version = "1.0.0"

  project = var.project

  namespace       = var.namespace
  service_account = var.service_accounttags = var.tags

  tags = var.tags
}
```

and variables :

```hcl
project = "foo-prod"

region = "europe-west1"

##############################################################################
# External DNS

namespace       = "dns"
service_account = "external-dns"
```

## Documentation

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 1.0.0 |
| <a name="requirement_aws"></a> [aws](#requirement\_aws) | >= 3.26.0 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | >= 3.26.0 |

## Modules

| Name | Source | Version |
|------|--------|---------|
| <a name="module_external_dns_role"></a> [external\_dns\_role](#module\_external\_dns\_role) | terraform-aws-modules/iam/aws//modules/iam-assumable-role-with-oidc | 5.0.0 |

## Resources

| Name | Type |
|------|------|
| [aws_iam_policy.dns](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_policy) | resource |
| [aws_eks_cluster.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/eks_cluster) | data source |
| [aws_iam_policy_document.dns](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/iam_policy_document) | data source |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_cluster_name"></a> [cluster\_name](#input\_cluster\_name) | Name of the EKS cluster | `string` | n/a | yes |
| <a name="input_namespace"></a> [namespace](#input\_namespace) | The Kubernetes namespace | `string` | n/a | yes |
| <a name="input_service_account"></a> [service\_account](#input\_service\_account) | The Kubernetes service account | `string` | n/a | yes |
| <a name="input_tags"></a> [tags](#input\_tags) | Tags for VPC | `map(string)` | <pre>{<br>  "made-by": "terraform"<br>}</pre> | no |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_role_arn"></a> [role\_arn](#output\_role\_arn) | Amazon Resource Name |
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
