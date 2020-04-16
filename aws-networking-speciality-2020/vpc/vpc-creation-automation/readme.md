# Automated VPC Creation
Based off https://github.com/aws-quickstart

# Goal
Create a multi-az, multi-tier (Public and Private Subnets) VPC that could be used as a basis for future labs/PoCs/tutorials across learning activities.

# VPC Configuration Options
- Availablilty Zones: Ability to specify 1 -> 3 Availability Zones (This is modeled off AP2 Region as this is where i will be deploying most of my workloads)
- Tier: 1 -> 2 extra private zones can be added.
- Network Restricted: Communication blocked by NACLs if enabled, able to add to Public or Private zones. 

# Pre-build Parameter Files

- aws-vpc-1az-1tier-network-open.json
- aws-vpc-1az-3tier-network-open.json
- aws-vpc-2az-2tier-network-open.json
- aws-vpc-3az-1tier-network-open.json
- aws-vpc-3az-3tier-network-open.json

# How to crate a new VPC - Example

``` 
aws cloudformation create-stack --profile "Update Profile to use" --stack-name "Stack Name To Deploy" --template-body file://"Path to repo"/aws-networking-speciality-2020/vpc/vpc-creation-automation/cfn/yaml/aws-vpc.template.yaml --parameters file://"Path to repo"/aws-networking-speciality-2020/vpc/vpc-creation-automation/cfn/params/aws-vpc-3az-3tier-network-open.json
```

# How to cleanup once you're done

``` 
aws cloudformation delete-stack --profile "Update Profile to use" --stack-name "Stack that has been deployed"
```