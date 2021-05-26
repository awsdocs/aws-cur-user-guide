# What are AWS Cost and Usage Reports?<a name="what-is-cur"></a>

The AWS Cost and Usage Reports \(AWS CUR\) contains the most comprehensive set of cost and usage data available\. You can use Cost and Usage Reports to publish your AWS billing reports to an Amazon Simple Storage Service \(Amazon S3\) bucket that you own\. You can receive reports that break down your costs by the hour, day, or month, by product or product resource, or by tags that you define yourself\. AWS updates the report in your bucket once a day in comma\-separated value \(CSV\) format\. You can view the reports using spreadsheet software such as Microsoft Excel or Apache OpenOffice Calc, or access them from an application using the Amazon S3 API\. 

AWS Cost and Usage Reports tracks your AWS usage and provides estimated charges associated with your account\. Each report contains line items for each unique combination of AWS products, usage type, and operation that you use in your AWS account\. You can customize the AWS Cost and Usage Reports to aggregate the information either by the hour, day, or month\.

AWS Cost and Usage Reports can do the following:
+ Deliver report files to your Amazon S3 bucket
+ Update the report up to three times a day
+ Create, retrieve, and delete your reports using the AWS CUR API Reference

## How Cost and Usage Reports work<a name="how-cur-works"></a>

Each update in a given month is cumulative, so each version of the Cost and Usage Reports includes all of the billing data for the month to date\. The reports generated throughout the month are estimated, and subject to change during the rest of the month as you continue to use your AWS services\. Different AWS services provide your usage\-based billing information at different times, so you may notice updates to a certain hour or day come in at different times\. AWS finalizes the Cost and Usage Report's usage charges at the end of the month after an invoice has been issued for your usage charges\. 

AWS might update reports after they have been finalized if AWS applies refunds, credits, or support fees to your usage for the month\. You can identify whether your anniversary bill charges have been finalized by referencing whether or not the **Bill/InvoiceId** column in your Cost and Usage Report has an Invoice ID for a line item\. If it does, those line items for the month are final and will not change\. Because Developer, Business and Enterprise Support are calculated based on final usage charges, those are reflected on the sixth or seventh of the month for the prior month’s Cost and Usage Report\. We apply credits or refunds based on the terms of your agreement or contract with AWS\.

## Using the data dictionary<a name="reading-cur"></a>

You can analyze your usage and cost in detail once you've set up your report\. We've provided a Data Dictionary that lists the columns you'll see in your report, along with definitions and examples\.

To see line item definitions, see the [Data dictionary](data-dictionary.md)\.

## Downloading AWS Cost and Usage Reports<a name="download-cur"></a>

You can download your report from the Amazon S3 console, query the report using Amazon Athena, or upload the report into Amazon Redshift or Amazon QuickSight\.
+ For more information about creating an Amazon S3 bucket and using Athena to query your data, see [Querying Cost and Usage Reports using Amazon Athena](cur-query-athena.md)\.
+ For more information about uploading to Amazon Redshift, see [Loading report data to Amazon Redshift](cur-query-other.md#cur-query-other-rs)\.
+ For more information about uploading to Amazon QuickSight, see [Loading report data to Amazon QuickSight](cur-query-other.md#cur-query-other-qs)\.

## AWS Organizations users<a name="cur-consolidated-billing"></a>

If you are either a management or member account in an organization in AWS Organizations, the Amazon S3 bucket that you designate to receive the billing reports must be owned by the account setting up the Cost and Usage Report\. The IAM policies governing the ability to setup a Cost and Usage Report are the same for both management and member accounts\. If a member account sets up a Cost and Usage Report, the member account will have access only to billing data for the time it has been a member of its current Organization\. For example, if a member account leaves organization A and joins organization B on the 15th of the month and then sets up a Cost and Usage report, report will only have billing data for the time the account has been a member of Organization B\. 

If you are an administrator of an AWS Organizations management account and do not want any of the member accounts in your Organization to set\-up a CUR you can do one of the following:
+ \(Recommended\) If you’ve opted into Organizations with all features enabled, you can apply a Service Control Policy \(SCP\)\. Note that SCPs only apply to member accounts and if you want to restrict any IAM users associated with the management account from setting up a CUR, you’ll need to adjust their specific IAM permissions\. SCPs also are not retroactive, so they will not de\-activate any CURs a member account may have set\-up prior to the SCP being applied\.
+ Submit a customer support case to block access to billing data in the Billing console for member accounts\. This is a list of organizations where the payer account prevents member accounts in its organization from viewing billing data on the **Bills** and **Invoices** pages\. This also prevents those accounts from setting up Cost and Usage Reports\. This option is only available for organizations without all features enabled\. Please note that if you have already opted into this to prevent member accounts from viewing bills and invoices in the Billing Console, you do not need to request this access again\. Those same member accounts will also be prevented from setting up a Cost and Usage Report\.

For more information on consolidated billing, see [Consolidated Billing for Organizations](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/consolidated-billing.html) in the *AWS Billing and Cost Management User Guide*\.