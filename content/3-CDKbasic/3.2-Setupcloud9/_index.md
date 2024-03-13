---
title : "Configure Cloud9 environment"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 3.2 </b> "
---

#### Configure Cloud9 environment

1. In the environment interface just initialized

   - Select the circular user icon in the right corner of the screen, next to **Share**
   - Select **Manage EC2 Instance**

![Amazon CDk](/images/2/0007.png?featherlight=false&width=90pc)

2. In the **EC2** interface

   - Select **Action**
   - Select **Security**
   - Select **Modify IAM role**

![Amazon CDk](/images/2/0008.png?featherlight=false&width=90pc)

3. In the **Modify IAM role** interface

   - Select the created role, this lab choose **CDK-Role**
   - Select **Update IAM role**

![Amazon CDk](/images/2/0009.png?featherlight=false&width=90pc)

4. Completed the role assignment successfully.

![Amazon CDk](/images/2/00010.png?featherlight=false&width=90pc)

5. In the view of the **AWS Cloud9** environment

   - Select **AWS Cloud9**
   - Select **Preferences**

![Amazon CDk](/images/2/00011.png?featherlight=false&width=90pc)

6. Cloud9 will manage IAM credentials automatically. We will need to disable this feature and use the IAM Role.

   - Select **AWS SETTINGS**
   - Select **Credentials**
   - Uncheck **AWS managed temporary credentials**

![Amazon CDk](/images/2/00012.png?featherlight=false&width=90pc)

7. Copy and Paste the command below into the Terminal of Cloud9 Workspace to install tools to support text processing on the command line.

```
sudo yum -y install jq gettext bash-completion moreutils
```

![Amazon CDk](/images/2/00013.png?featherlight=false&width=90pc)

8. Similar to CloudFormation, you can install the cfn-lint tool to help you check CDK templates and other information, including auditing.
Check if the resource properties are correct or not
configured according to best practices or not.

```
pip install cfn-lint
```

![Amazon CDk](/images/2/00014.png?featherlight=false&width=90pc)

9. Check the successful installation of cfn-lint using the following command:

```
cfn-lint --version
```

![Amazon CDk](/images/2/00015.png?featherlight=false&width=90pc)

10. We will configure the aws cli to use the current Region.

```
export ACCOUNT_ID=$(aws sts get-caller-identity --output text --query Account)
export AWS_REGION=$(curl -s 169.254.169.254/latest/dynamic/instance-identity/document | jq -r '.region')
export AZS=($(aws ec2 describe-availability-zones --query 'AvailabilityZones[].ZoneName' --output text --region $AWS_REGION))
```

![Amazon CDk](/images/2/00016.png?featherlight=false&width=90pc)

11. We will save the configuration information to bash_profile

```
echo "export ACCOUNT_ID=${ACCOUNT_ID}" | tee -a ~/.bash_profile

echo "export AWS_REGION=${AWS_REGION}" | tee -a ~/.bash_profile

echo "export AZS=(${AZS[@]})" | tee -a ~/.bash_profile

aws configure set default.region ${AWS_REGION}
```

![Amazon CDk](/images/2/00017.png?featherlight=false&width=90pc)

12. Check if CLI CDK is installed by running the command.

```
cdk --version
```

![Amazon CDk](/images/2/00018.png?featherlight=false&width=90pc)

13. We will use the command to check if the Cloud9 IDE is using the IAM Role correctly.

```
aws sts get-caller-identity --query Arn | grep CDK-Role -q && echo "IAM role valid" || echo "IAM role NOT valid"
```