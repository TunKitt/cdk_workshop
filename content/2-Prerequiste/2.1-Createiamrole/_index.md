---
title : "Create IAM Role"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 2.1 </b> "
---

#### Create IAM Role

1. Access the [AWS Management Console] interface(https://aws.amazon.com/console/)

   - Find **IAM**
   - Select **IAM**

![Amazon CDk](/images/1/0001.png?featherlight=false&width=90pc)

2. In the **IAM** interface


   - Select **Roles**
   - Select **Create role**

![Amazon CDk](/images/1/0002.png?featherlight=false&width=90pc)

3. In the **Select trusted entity** interface

   - Select **AWS service**
   - **Use case**, select **EC2**
   - Select **Next**

![Amazon CDk](/images/1/0003.png?featherlight=false&width=90pc)

4. In the **Create role** interface

   - Find the policy **AdministratorAccess**
   - Select the policy **AdministratorAccess**
   - Select **Next**

![Amazon CDk](/images/1/0004.png?featherlight=false&width=90pc)

5. In the **Role details** interface

   - **Role name**, enter `CDK-Role`

![Amazon CDk](/images/1/0005.png?featherlight=false&width=90pc)

6. Select **Create role**

![Amazon CDk](/images/1/0006.png?featherlight=false&width=90pc)

7. Complete role creation

![Amazon CDk](/images/1/0007.png?featherlight=false&width=90pc)