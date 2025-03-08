### Terraform Blocks-
Terraform uses a variety of "blocks" to define infrastructure resources and configurations. Here are some common Terraform blocks:


* Provider Block *-
Specifies the provider (e.g., AWS, Azure, Google Cloud) and its configuration.
```
provider "aws" {
  region = "us-west-2"
}
```

Resource Block

Defines the infrastructure resource to be created.

hcl
resource "aws_instance" "example" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t2.micro"
}
Variable Block

Defines input variables to parameterize configurations.

hcl
variable "instance_type" {
  description = "Type of EC2 instance"
  type        = string
  default     = "t2.micro"
}
Output Block

Defines output values to be returned after applying the configuration.

hcl
output "instance_id" {
  value = aws_instance.example.id
}
Module Block

References and configures a module to reuse configurations.

hcl
module "vpc" {
  source = "terraform-aws-modules/vpc/aws"
  version = "2.77.0"

  name = "my-vpc"
  cidr = "10.0.0.0/16"
}
Locals Block

Defines local values to simplify and reduce repetition in configurations.

hcl
locals {
  instance_count = 3
}
Data Block

Retrieves or queries data from an external source.

hcl
data "aws_ami" "latest" {
  most_recent = true
  owners      = ["self"]
}
These blocks are the building blocks of Terraform configurations and enable you to define, manage, and organize your infrastructure as code.
