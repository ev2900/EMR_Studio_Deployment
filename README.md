# EMR Studio CloudFormation Deployment

The instructions below show you how to deploy and set EMR Studio with single sign on (SSO).

1. Enable SSO for your AWS account, if it is now already enabled

Go to [IAM Identity Center (successor to AWS Single Sign-On)](https://us-east-1.console.aws.amazon.com/singlesignon/identity/home). Click the **Enable** button

<img width="700" alt="Fluentd_cloud9_Architecture" src="https://github.com/ev2900/EMR_Studio_CloudFormation_Deployment/blob/main/Architecture/SSO.png">

2. Run the CloudFormation stack. It will create the required resources required for this example

[![Launch CloudFormation Stack](https://sharkech-public.s3.amazonaws.com/misc-public/cloudformation-launch-stack.png)](https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=dynamo-lambda-opensearch&templateURL=https://sharkech-public.s3.amazonaws.com/misc-public/emr_studio_demo.yaml)

The resources created by the CloudFormation stack are documented in the architecture below

