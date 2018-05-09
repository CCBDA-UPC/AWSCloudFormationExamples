# AWS CloudFormation examples

run the first example using AWS cli or upload it to the [AWS CloudFormation console](https://eu-west-1.console.aws.amazon.com/cloudformation/).

```
_$ aws cloudformation create-stack --stack-name firstStack --parameters ParameterKey=KeyName,ParameterValue=ccbda_upc ParameterKey=SSHLocation,ParameterValue=192.168.0.1/32 --template-body https://raw.githubusercontent.com/angeltoribio-UPC-BCN/CloudFormationExamples/master/FirstTemplate.json

{
    "StackId": "arn:aws:cloudformation:eu-west-1:YOUR-AWS-ID:stack/firstStack/7c90e740-5207-11e8-9cb4-503ac9eaaa35"
}


_$ aws cloudformation list-stack-resources --stack-name firstStack
{
    "StackResourceSummaries": [
        {
            "ResourceType": "AWS::EC2::Instance",
            "PhysicalResourceId": "i-05d8977ec5afe29fb",
            "LastUpdatedTimestamp": "2018-05-07T16:01:30.525Z",
            "ResourceStatus": "CREATE_COMPLETE",
            "LogicalResourceId": "WebServerEC2Instance"
        },
        {
            "ResourceType": "AWS::EC2::SecurityGroup",
            "PhysicalResourceId": "firstStack-WebServerSecurityGroup-ZT2SOUNS6748",
            "LastUpdatedTimestamp": "2018-05-07T16:00:54.236Z",
            "ResourceStatus": "CREATE_COMPLETE",
            "LogicalResourceId": "WebServerSecurityGroup"
        }

_$ aws cloudformation delete-stack --stack-name firstStack
```

[More examples from AWS](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/sample-templates-services-us-west-2.html)