# AWS CloudFormation Examples

These examples accompany my [AWS Community Day Instanbul 2023](https://aws.cloudturkey.io/) talk.
[Optimising EC2 AutoScaling Groups in CloudFormation](https://b3cft.url.lol/aws-slides-2023-05)

## Prerequisites

1. AWS Account
2. AWS Credentials with permissions to run CloudFormation, create VPCs, IAM Role, AutoScaling Groups etc.
3. AWS CLI tools installed
4. EC2 Key Pair created

## Setup VPC

Checkout this github repo.

From the AWS Console, locate the name of the EC2 KeyPair you wish to use and add keep it for the Initial Setup.

Decide on a CIDR to use for the example VPC (temporary, you can delete it later).
Currently support a `10.x.0.0/16` CIDR. So substitue a number for `x`

### Initial SSM Parameters

```bash
cd example-vpc
make update-parameter NAME=/base/example/ec2-keyname   VALUE=<<Insert Key name here>>
make update-parameter NAME=/example-vpc/cidr           VALUE=<<CIDR here. e.g. 10.10.0.0/16>>
make update-parameter NAME=/example-vpc/single-nat     VALUE=true
```

That last parameter `single-nat` will create a single EC2 NAT Gateway instance. An `amz2-arm64` `t4g.micro` instance.
Set the value to `false` and it will create 3 instances, one for AZs `a`, `b` and `c` instead.

### Launch VPC

Once the above parameters are set run

```bash
make create-stack
```

After a couple of minutes, the VPC should be created.

```bash
make show-outputs
```

should then list the VPC and subnet details.

## Launch ASG example

From the checkout root.

```bash
cd example-vpc
make set-default-params
```

This will create a default set of parameters for using the example template.

Run:

```bash
make show-ssm-parameters
```

to view the settings.

