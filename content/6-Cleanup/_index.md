---
title : "Clean up resources"
date : "`r Sys.Date()`"
weight : 6
chapter : false
pre : " <b> 6. </b> "
---

#### Clean up resources

Congratulations on completing the basic CDK workshop. To summarize, you have

- Install and familiarize yourself with CDK CLI
- Use CDK to deploy a simple infrastructure, including
    - VPC
    - Public subnet
    - EC2 instances
    - Roles and Security groups
    - Install Apache on EC2 instance via user data

Don't forget to delete the created resources. There are two ways you can clean up resources:

- Delete CloudFormation stack on AWS console
- Use CDK CLI to delete stack

```
cdk destroy
```

![Amazon CDk](/images/4/00012.png?featherlight=false&width=90pc)

- Remember to delete Cloud9 Instance after you delete the CDK stack.
