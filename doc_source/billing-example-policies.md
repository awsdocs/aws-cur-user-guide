# AWS CUR Policy Examples<a name="billing-example-policies"></a>

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
These policies require that you activate IAM user access to the Billing and Cost Management console on the [Account Settings](https://portal.aws.amazon.com/billing/home#/account) console page\. For more information, see [Activating Access to the Billing and Cost Management Console](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/control-access-billing.html#ControllingAccessWebsite-Activate) in the *AWS Billing and Cost Management User Guide*\.

**Example Topics**
+ [Example 1: Allow IAM users to access the Reports console page](#example-billing-view-reports)
+ [Example 2: Create, view, edit, or delete AWS Cost and Usage Reports](#example-policy-report-definition)

## Example 1: Allow IAM users to access the Reports console page<a name="example-billing-view-reports"></a>

To allow an IAM user to access the **Cost & Usage Reports** console page and to view the usage reports that contain account activity information, use a policy similar to this example policy\.

For definitions of each action, see [Billing Actions](billing-permissions-ref.md#user-permissions), or [User Types and Billing Permissions](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-permissions-ref.html#user-types) in the *AWS Billing and Cost Management User Guide*\.

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

## Example 2: Create, view, edit, or delete AWS Cost and Usage Reports<a name="example-policy-report-definition"></a>

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