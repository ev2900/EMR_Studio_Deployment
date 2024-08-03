# EMR Studio CloudFormation Deployment

<img width="275" alt="map-user" src="https://img.shields.io/badge/cloudformation template deployments-4-blue"> <img width="85" alt="map-user" src="https://img.shields.io/badge/views-141-green"> <img width="125" alt="map-user" src="https://img.shields.io/badge/unique visits-045-green">

The instructions below show you how to deploy and set EMR Studio with single sign on (SSO).

1. Enable SSO for your AWS account, if it is now already enabled
* Go to [IAM Identity Center (successor to AWS Single Sign-On)](https://us-east-1.console.aws.amazon.com/singlesignon/identity/home)
* Click the **Enable** button
* Click through the prompts

2. Run the CloudFormation stack. It will create the required resources required for this example

[![Launch CloudFormation Stack](https://sharkech-public.s3.amazonaws.com/misc-public/cloudformation-launch-stack.png)](https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=emr-studio-demo&templateURL=https://sharkech-public.s3.amazonaws.com/misc-public/emr_studio_demo.yaml)

The resources created by the CloudFormation stack are documented in the architecture below

<img width="700" alt="Architecture" src="https://github.com/ev2900/EMR_Studio_CloudFormation_Deployment/blob/main/Architecture/emr-studio-architecture.png">

3. Create a SSO User
* Go to [IAM Identity Center (successor to AWS Single Sign-On) User Page](https://us-east-1.console.aws.amazon.com/singlesignon/identity/home?region=us-east-1#!/users)
* Click the **Add user** button
* Click through the prompts

4. Add a user to the EMR studio
* Go to [EMR Studio Home Page](https://us-east-1.console.aws.amazon.com/emr/home?region=us-east-1#/studios)
* Click on the studio named **EMR-Studio-Demo**
* Click on **add users*** and select the SSO user you created

5. Assign policy to the user
* Go to [EMR Studio Home Page](https://us-east-1.console.aws.amazon.com/emr/home?region=us-east-1#/studios)
* Click on the studio named **EMR-Studio-Demo**
* Select the bubble next to the SSO user
* Click on the **Assign policy** button
* Apply the *advanced-user-policy-emr-studio* to the user

6. Log into EMR studio

## Create Default EMR Roles

If you have never created a EMR cluster in your account before you may not have the *EMR_DefaultRole* and *EMR_EC2_DefaultRole* roles. To create these you can execute the following aws CLI command.

If you don't have the AWS CLI set up locally you can run this command via. CloudShell

```aws emr create-default-roles```

You may also need to create the *AWSServiceRoleForEMRCleanup* if you do not already have this role created. To create this role

* Go to [IAM Console Page](https://us-east-1.console.aws.amazon.com/iamv2/home?region=us-east-1#/roles)
* Click on roles, create role, AWS service, EMR, **EMR - Clean Up**
* Click through the prompts and create the role

These roles (*EMR_DefaultRole*, *EMR_EC2_DefaultRole*, *AWSServiceRoleForEMRCleanup*) are required for users to create EMR clusters via. EMR studio

## Future Imporvement to this Repo
* Service catalog intergration
