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
| terraform | >= 1.0.0 |
| aws | >= 3.26.0 |

## Providers

| Name | Version |
|------|---------|
| aws | >= 3.26.0 |

## Modules

| Name | Source | Version |
|------|--------|---------|
| external_dns_role | terraform-aws-modules/iam/aws//modules/iam-assumable-role-with-oidc | 4.7.0 |

## Resources

| Name |
|------|
| [aws_eks_cluster](https://registry.terraform.io/providers/hashicorp/aws/3.26.0/docs/data-sources/eks_cluster) |
| [aws_iam_policy](https://registry.terraform.io/providers/hashicorp/aws/3.26.0/docs/resources/iam_policy) |
| [aws_iam_policy_document](https://registry.terraform.io/providers/hashicorp/aws/3.26.0/docs/data-sources/iam_policy_document) |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| cluster\_name | Name of the EKS cluster | `string` | n/a | yes |
| namespace | The Kubernetes namespace | `string` | n/a | yes |
| service\_account | The Kubernetes service account | `string` | n/a | yes |
| tags | Tags for VPC | `map(string)` | <pre>{<br>  "made-by": "terraform"<br>}</pre> | no |

## Outputs

| Name | Description |
|------|-------------|
| role\_arn | Amazon Resource Name |
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
