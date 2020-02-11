# Identity and Access Management for AWS Cost and Usage Reports<a name="security-iam"></a>

AWS Identity and Access Management \(IAM\) is an AWS service that helps an administrator securely control access to AWS resources\. IAM administrators control who can be *authenticated* \(signed in\) and *authorized* \(have permissions\) to use AWS CUR resources\. IAM is an AWS service that you can use with no additional charge\.

For more information on how to activate access to the Billing Console, see [Tutorial: Delegate Access to the Billing Console](https://docs.aws.amazon.com/IAM/latest/UserGuide/tutorial_billing.html) in the *IAM User Guide*\.

For IAM details for using the Billing Console, see [Overview of Managing Access Permissions](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/control-access-billing.html) in the *AWS Billing and Cost Management User Guide*\.

**Topics**
+ [Audience](#security_iam_audience)
+ [Overview of Managing Access Permissions](control-access-billing.md)
+ [Using Identity\-Based Policies \(IAM Policies\) for AWS CUR](billing-permissions-ref.md)
+ [AWS CUR Policy Examples](billing-example-policies.md)

## Audience<a name="security_iam_audience"></a>

How you use AWS Identity and Access Management \(IAM\) differs, depending on the work you do in AWS CUR\.

**Service user** – If you use the AWS CUR service to do your job, then your administrator provides you with the credentials and permissions that you need\. As you use more AWS CUR features to do your work, you might need additional permissions\. Understanding how access is managed can help you request the right permissions from your administrator\.

**Service administrator** – If you're in charge of AWS CUR resources at your company, you probably have full access to AWS CUR\. It's your job to determine which AWS CUR features and resources your employees should access\. You must then submit requests to your IAM administrator to change the permissions of your service users\. Review the information on this page to understand the basic concepts of IAM\.

**IAM administrator** – If you're an IAM administrator, you might want to learn details about how you can write policies to manage access to AWS CUR\.

This table summarizes the default actions that are permitted in AWS CUR for each type of billing user\.


**User Types and Billing Permissions**  

| User Type | Description | Billing Permissions | 
| --- | --- | --- | 
| Account owner |  The person or entity in whose name your account is set up as\.  |  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/cur/latest/userguide/security-iam.html)  | 
| IAM user |  A person or application defined as a user in an account by an account owner or administrative user\. Accounts can contain multiple IAM users\.  |  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/cur/latest/userguide/security-iam.html)  | 
| Organization master account owner |  The person or entity associated with an AWS Organizations master account\. The master account pays for AWS usage that is incurred by a member account in an organization\.   |  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/cur/latest/userguide/security-iam.html)  | 
| Organization member account owner |  The person or entity associated with an AWS Organizations member account\. The master account pays for AWS usage that is incurred by a member account in an organization\.   |  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/cur/latest/userguide/security-iam.html)  | 