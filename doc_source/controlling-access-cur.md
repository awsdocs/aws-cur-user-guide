# Controlling Access<a name="controlling-access-cur"></a>

To perform any operation on AWS Cost and Usage Reports resources, AWS Identity and Access Management \(IAM\) controls your access to Billing and Cost Management by verifying that you have permissions to perform these operations\. If you're an account administrator, you can use IAM to control the access of other users to the resources that are associated with your account\.

This page summarizes the default actions that are permitted in Billing and Cost Management for each type of AWS CUR user, and the permissions that you can apply to your IAM users\. The reference also provides examples of policies that you can use to allow or deny an IAM user access to your billing information and tools\. 

AWS Billing and Cost Management integrates with the AWS Identity and Access Management \(IAM\) service so that you can control who in your organization has access to specific pages on [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\. 

For a full discussion of AWS accounts and IAM users, see [What Is IAM?](https://docs.aws.amazon.com/IAM/latest/UserGuide//IAM_Introduction.html) in the *IAM User Guide*\.

## Actions<a name="cur-iam-actions"></a>

This table summarizes the permissions that allow or deny IAM users access to your AWS CUR\. For examples of policies that use these permissions, see [AWS Cost and Usage Reports Policy Examples](#cur-example-policies)\. 

AWS CUR permissions apply to all reports created using the [AWS Cost and Usage Reports Service](https://docs.aws.amazon.com/Iaws-cost-management/latest/APIReference/API_Operations_AWS_Cost_and_Usage_Report_Service.html) API and the Billing and Cost Management console\. If you create reports using the Billing and Cost Management console, we recommend that you update the permissions for IAM users\. Not updating the permissions will result in users losing access to viewing, editing, and removing reports on the console reports page\.


| Permission Name | Description | 
| --- | --- | 
|  `cur:DescribeReportDefinitions`  |  Allow or deny IAM users permission to view AWS Cost and Usage Reports\.  | 
|  `cur:PutReportDefinition`  |  Allow or deny IAM users permission to create AWS Cost and Usage Reports\.  | 
|  `cur:DeleteReportDefinition`  |  Allow or deny IAM users permission to delete AWS Cost and Usage Reports using the API\.  | 
| cur:ModifyReportDefinition |  Allow or deny IAM users permission to modify AWS Cost and Usage Reports\.  | 

## AWS Cost and Usage Reports Policy Examples<a name="cur-example-policies"></a>

This topic contains example policies that you can attach to your IAM user or group to control access to your account's billing information and tools\. The following basic rules apply to IAM policies for Billing and Cost Management:
+ `Version` is always `2012-10-17`\.
+ `Effect` is always `Allow` or `Deny`\.
+ `Action` is the name of the action or a wildcard \(`*`\)\. 

  For consoles, the action prefix in China is `awsbillingconsole`\. Everywhere else, it's `aws-portal`\.

  The action prefix is `cur` for AWS Cost and Usage Reports\.
+ `Resource` is always `*` for AWS Billing\.

  For actions performed on a `budget` resource, specify the budget Amazon Resource Name \(ARN\)\.
+ It's possible to have multiple statements in one policy\.

**Note**  
These policies require that you activate IAM user access to the Billing and Cost Management console on the [Account Settings](https://portal.aws.amazon.com/billing/home#/account) console page\. For more information, see [Activating Access](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/grantaccess.html) in the *AWS Billing and Cost Management User Guide*\.

### Example 1: Allow IAM users to access the Reports console page<a name="example-billing-view-reports"></a>

To allow an IAM user to access the **Cost & Usage Reports** console page and to view the usage reports that contain account activity information, use a policy similar to this example policy\.

For definitions of each action, see [User Types and Billing Permissions](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-permissions-ref.html#user-types) in the *AWS Billing and Cost Management User Guide*\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "aws-portal:ViewUsage",
                "aws-portal:ViewBilling",
                "cur:DescribeReportDefinitions",
                "cur:PutReportDefinition",
                "cur:DeleteReportDefinition",
                "cur:ModifyReportDefinition"
            ],
            "Resource": "*"
        }
    ]
}
```

### Example 2: Create, view, edit, or delete AWS Cost and Usage Reports<a name="example-policy-report-definition"></a>

This policy allows an IAM user to create, view, edit, or delete `sample-report` using the API\.

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "ManageSampleReport",
            "Action": [
                "cur:PutReportDefinition", 
                "cur:DeleteReportDefinition",
                "cur:ModifyReportDefinition"
            ],
            "Resource": "arn:aws:cur:*:123456789012:definition/sample-report"
        },
        {
            "Sid": "DescribeReportDefs",
            "Effect": "Allow",
            "Action": "cur:DescribeReportDefinitions",
            "Resource": "*"
        }
    ]
}
```