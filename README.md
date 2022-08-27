# AWS Terraform


# Managing AWS Infrastructure using Terraform

The purpose of this project is to create an entire AWS infrastructure using Terraform. We will create VPC, subnets, network interfaces, and AMI's using AWS.



## Installation

Install Terraform

```bash
  brew tap hashicorp/tap
```
```bash
  brew install hashicorp/tap/terraform
```

```bash
  brew update
```

```bash
  brew upgrade hashicorp/tap/terraform
```



## Build Infrastructure

Make the directory

```bash
  mkdir learn-terraform-aws-instance
```

Go to the project directory

```bash
  cd learn-terraform-aws-instance
```

Create a file to define your Infrastructure

```bash
  touch main.tf
```

Open main.tf and paste the code:

```bash
  terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 4.16"
    }
  }

  required_version = ">= 1.2.0"
}

provider "aws" {
  region  = "us-west-2"
}

resource "aws_instance" "app_server" {
  ami           = "ami-830c94e3"
  instance_type = "t2.micro"

  tags = {
    Name = "ExampleAppServerInstance"
  }
}
```

Initialize the directory

```bash
  terraform init
```
Format and validate the configuration

```bash
  terraform fmt
```
```bash
  terraform validate
```
Create infrastructure

```bash
  terraform apply
```
## Change Infrastructure


Create a directory named learn-terraform-aws-instance and paste the following configuration into a file named main.tf.
```bash
  terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 4.16"
    }
  }

  required_version = ">= 1.2.0"
}

provider "aws" {
  region  = "us-west-2"
}

resource "aws_instance" "app_server" {
  ami           = "ami-830c94e3"
  instance_type = "t2.micro"

  tags = {
    Name = "ExampleAppServerInstance"
  }
}


```
Initialize the configuration.
```bash
terraform init
```
Apply the configuration. Respond to the confirmation prompt with a yes.

```bash
terraform apply
```

Configuration

Update the ami of your instance. Change the AMI ID under the aws_instance.app_server provider block in main.tf by replacing the current AMI ID with a new one.
```bash
Tip: The below snippet is formatted as a diff to give you context about which parts of your configuration you need to change. Replace the content displayed in red with the content displayed in green, leaving out the leading + and - signs.
```
```bash
 resource "aws_instance" "app_server" {
-  ami           = "ami-830c94e3"
+  ami           = "ami-08d70e59c07c61a3a"
   instance_type = "t2.micro"
 }
 ```
 Apply Changes
 ```bash
 terraform apply
 ```
 Destroy Infrastructure

```bash
terraform destroy
```
## Documentation

[Hashicorp Documentation](https://learn.hashicorp.com/tutorials/terraform/infrastructure-as-code?in=terraform/aws-get-started)


## Authors

- [@johngeorge](https://github.com/johngeorge142/)

