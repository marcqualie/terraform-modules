# DBL Terraform Modules

We create modules here for re-use between projects.



## Modules

- [certificate](certificate/README.md) - Requests a certificate from the Amazon Certificate Manager.
- [cloudwatch](cloudwatch/README.md) - Creates basic cloudwatch dashboard and cloudwatch alarm for monitoring and observability
- [cognito](cognito/README.md) - Create user pools for use with authentication.
- [ecr](ecr/README.md) - A repository for storing built docker images.
- [ecs](ecs/README.md) - Compute cluster for running docker containers.
- [elasticache](elasticache/README.md) - elasticache cluster based on Redis.
- [global-accelerator](global-accelerator/README.md) - Global Accelerator for load balancing across multiple regions.
- [iam](iam/README.md) - Preconfigured IAM groups and roles for sane access policies.
- [kms-key](kms-key/README.md) - Encryption keys for securing various AWS resources.
- [kms-key-replica](kms-key-replica/README.md) - KMS Key replica for cross-regional access to encryption keys.
- [nat](nat/README.md) - A reopsitory for setting up a network address translation (NAT).
- [rds](rds/README.md) - Used for creating and configuring databases and their networking.
- [s3-private](s3-private/README.md) - Private, encrypted S3 bucket with versioning.
- [s3-public](s3-public/README.md) - S3 bucket to host public files such as a frontend app, or anything you want to servce via a CDN.
- [slack](slack/README.md) - Creates chatbot and SNS topic required to setup Slack message
- [snowflake-cloud](snowflake/cloud/README.md) - Manage a Snowflake Cloud account
- [secrets](secrets/README.md) - Used for creating a new secret.
- [stack](stack/README.md) - Creates all resources required to launch the entire application
- [vpc](vpc/README.md) - Creates a VPC in AWS account. Also generates a group fo public and private submodules.
- [vpc-peering](vpc-peering/README.md) - Creates a VPC Peering Resource.
- [vpn](vpn/README.md) - Launches an isolated Outline VPN inside a new VPC.
- [xray](xray/README.md) - Used for creating general xray group and sampling



## Conventions

- Use `project` + `environment` combination for a workspace/module context
- Use `main` for core resource identifiers. e.g. `resource "aws_rds_instance" "main" {}`



## Usage

Refer to specific module README for variables and recommended usage.

```terraform
module "awesome-module" {
  source = "github.com/dbl-works/terraform//awesome-module?ref=v2021.07.05"

  # Required
  environment = "staging"
  project     = "someproject"

  # Optional
  some_variable = "some_value"
}
```
