# Setting Up an Amazon S3 Bucket for Cost and Usage Reports<a name="cur-s3"></a>

 To receive billing reports, you must have an Amazon S3 bucket in your AWS account to store your reports\. You can specify an existing bucket or create one\. To create a bucket, see [Creating a Bucket](https://docs.aws.amazon.com/AmazonS3/latest/user-guide/CreatingaBucket.html) in the *[Amazon Simple Storage Service Console User Guide](https://docs.aws.amazon.com/AmazonS3/latest/user-guide/)*\.

You also need to apply a resource\-based permissions policy to your Amazon S3 bucket to allow AWS to write files to the bucket\. For an example bucket policy and information about how to apply your policy to a bucket, see [Step 2: Turn on Reports](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-getting-started.html#step-2) in the *AWS Billing and Cost Management User Guide*\.

## Rates<a name="cur-s3-rates"></a>

Storing the billing reports data in your Amazon S3 bucket is billed at standard Amazon S3 rates\. For more information, see [Quotas and Restrictions](billing-cur-limits.md)\.