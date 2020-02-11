# Using Identity\-Based Policies \(IAM Policies\) for AWS CUR<a name="billing-permissions-ref"></a>

This topic provides examples of identity\-based policies that demonstrate how an account administrator can attach permissions policies to IAM identities \(users, groups, and roles\) and thereby grant permissions to perform operations on AWS CUR resources\.

For a full discussion of AWS accounts and IAM users, see [What Is IAM?](https://docs.aws.amazon.com/IAM/latest/UserGuide/IAM_Introduction.html) in the *IAM User Guide*\.

## Billing Actions<a name="user-permissions"></a>

This table summarizes the permissions that allow or deny IAM users access to your billing information and tools\. For examples of policies that use these permissions, see [AWS CUR Policy Examples](billing-example-policies.md)\. 

AWS CUR permissions apply to all reports created using the [AWS Cost and Usage Reports Service](https://docs.aws.amazon.com/Iaws-cost-management/latest/APIReference/API_Operations_AWS_Cost_and_Usage_Report_Service.html) API and the Billing and Cost Management console\. If you create reports using the Billing and Cost Management console, we recommend that you update the permissions for IAM users\. Not updating the permissions will result in users losing access to viewing, editing, and removing reports on the console reports page\.


| Permission Name | Description | 
| --- | --- | 
|  `cur:DescribeReportDefinitions`  |  Allow or deny IAM users permission to view AWS Cost and Usage Reports\.  | 
|  `cur:PutReportDefinition`  |  Allow or deny IAM users permission to create AWS Cost and Usage Reports\.  | 
|  `cur:DeleteReportDefinition`  |  Allow or deny IAM users permission to delete AWS Cost and Usage Reports using the API\.  | 
| cur:ModifyReportDefinition |  Allow or deny IAM users permission to modify AWS Cost and Usage Reports\.  | 