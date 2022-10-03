# EMR Studio CloudFormation Deployment

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
