# Creating Cost and Usage Reports<a name="cur-create"></a>

You can use the **Cost & Usage Reports** page of the Billing and Cost Management console to create Cost and Usage Reports\.

**Note**  
It can take up to 24 hours for AWS to start delivering reports to your Amazon S3 bucket\. After delivery starts, AWS updates the AWS Cost and Usage Reports files at least once a day\.<a name="create-cur-steps"></a>

**To create Cost and Usage Reports**

1. Sign in to the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/home\#/](http://console.aws.amazon.com/billing)

1. On the navigation pane, choose **Cost & Usage Reports**\.

1. Choose **Create report**\.

1. For **Report name**, enter a name for your report\.

1. For **Additional report details**, select **Include resource IDs** to include the IDs of each individual resource in the report\.
**Note**  
Including resource IDs will create individual line items for each of your resources\. This can increase the size of your Cost and Usage Reports files significantly, based on your AWS usage\.

1. For **Data refresh settings**, select whether you want the AWS Cost and Usage Reports to refresh if AWS applies refunds, credits, or support fees to your account after finalizing your bill\. When a report refreshes, a new report is uploaded to Amazon S3\.

1. Choose **Next**\.

1. For **S3 bucket**, choose **Configure**\.

1. In the **Configure S3 Bucket** dialog box, do one of the following:
   + Select an existing bucket from the drop down list and choose **Next**\.
   + Enter a bucket name and the Region where you want to create a new bucket and choose **Next**\.

1. Review the bucket policy, and select **I have confirmed that this policy is correct** and choose **Save**\.

1. For **Report path prefix**, enter the report path prefix that you want prepended to the name of your report\. 

1. For **Time granularity**, choose one of the following:
   + **Hourly** if you want the line items in the report to be aggregated by the hour\.
   + **Daily** if you want the line items in the report to be aggregated by the day\.
   + **Monthly** if you want the line items in the report to be aggregated by month\.

1. For **Report versioning**, choose whether you want each version of the report to overwrite the previous version of the report or to be delivered in addition to the previous versions\.

   Overwriting reports can save on Amazon S3 storage costs\. Delivering new report versions can improve auditability of billing data over time\.

1. For **Enable report data integration for**, select whether you want to enable your Cost and Usage Reports to integrate with Amazon Athena, Amazon Redshift, or Amazon QuickSight\. The report is compressed in the following formats:
   + **Athena**: parquet format
   + **Amazon Redshift or Amazon QuickSight**: \.gz compression

1. Choose **Next**\.

1. After you have reviewed the settings for your report, choose **Review and Complete**\. 

You can always return to the Cost & Usage Reports section of your Billing and Cost Management console to see when your reports were last updated\.