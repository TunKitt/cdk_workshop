---
title : "CDK Basic"
date : "`r Sys.Date()`"
weight : 1
chapter : false
---

# CDK basic

#### Overview

CloudFormation is a service that allows users to deploy application architecture in code (Infrastructure as code). Users can write JSON or YAML files to deploy all AWS services (VPC, EC2, Lambda,...). A collection of AWS resources will be deployed across a CloudFormation Stack, and you can easily manage instances, create new instances, or delete all associated resources. The whole process can be automatically generated and is completely free (you only need to pay for the resources created below).

The AWS Cloud Development Kit (CDK) is an AWS service based on CloudFormation. However, with CDK, users can define the architecture of AWS resources in popular programming languages ​​such as TypeScript, JavaScript, Python, Java, C#

{{< figure src="/images/serviceicon.png" title="AWS Cloud Development Kit (AWS CDK)" width=150pc >}}

In this lab, we will practice using the CDK. After completing the lab, the reader will be able to

- Understand the basic concepts of CDK
- Deploy a basic architecture to AWS using CDK
- Configure EC2 through user data

Before doing this workshop on CDK, you should do the CloudFormation workshop to understand a few basic concepts, because CDK actually **works. Dynamically based on CloudFormation**


#### Content

1. [Introduction](1-introduce/)
2. [Preparation](2-prerequiste/)
3. [Basic CDK](3-cdkbasic/)
4. [Create CDK Template](4-createcdktemplate/)
5. [Update CDK Template](5-updatecdktemplate/)
6. [Resource Cleanup](6-cleanup/)