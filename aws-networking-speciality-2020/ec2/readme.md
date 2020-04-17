# EC2 Cloudformation Examples

# Goal
Repeatable way to create EC2s in target VPCs 

# EC2 Configuration Options
- KeyName
- InstanceType
- SourceCIDRRange
- TargetSubnetID
- AMI
- TargetVPCID
- EC2Tag1
- EC2Tag2
- EC2Tag3

# Pre-build Parameter Files

- simple-webserver.json

# How to crate a new VPC - Example

``` 
aws cloudformation create-stack --profile "update-me" --stack-name "update-me" --template-body file://"update-me"/public-ec2-wtih-securitygroup.yaml --parameters file://"update-me"/simple-webserver.json
```

# How to cleanup once you're done

``` 
aws cloudformation delete-stack --profile "update-me" --stack-name "update-me"
```