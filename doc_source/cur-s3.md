# Setting up an Amazon S3 bucket for Cost and Usage Reports<a name="cur-s3"></a>

To receive billing reports, you must have an Amazon S3 bucket in your AWS account to receive and store your reports\. When setting up a Cost and Usage Report in the billing console you can select an existing Amazon S3 bucket you own or setup up a new one\. In either case, you’ll be asked to review and confirm the application of the following default bucket policy\. Editing this policy in the Amazon S3 console or changing the bucket owner after you’ve setup a Cost and Usage Report will prevent AWS from being able to deliver your reports\. Storing the billing reports data in your Amazon S3 bucket is billed at standard Amazon S3 rates\. For more information, see [Quotas and restrictions](billing-cur-limits.md)\.

The following policy is applied to every bucket during the setup of a Cost and Usage Report:

```
{
  "Version": "2012-10-17",
  "Statement": [
  {
    "Effect": "Allow",
    "Principal": {
      "Service": "billingreports.amazonaws.com"
    },
    "Action": [
      "s3:GetBucketAcl",
      "s3:GetBucketPolicy"
    ],
    "Resource": "arn:aws:s3:::DOC-EXAMPLE-BUCKET"
  },
  {
    "Effect": "Allow",
    "Principal": {
      "Service": "billingreports.amazonaws.com"
    },
    "Action": "s3:PutObject",
    "Resource": "arn:aws:s3:::DOC-EXAMPLE-BUCKET/*"
  }
  ]
}
```

This default policy helps ensure that the Cost and Usage Report data can be read by the bucket owner and confirms the bucket is owned by the account which set\-up the Cost and Usage Report\. Specifically: 
+ Every time a Cost and Usage Report is delivered, AWS first confirms whether the bucket is still owned by the account which setup the report\. If the bucket ownership has changed, the report will not be delivered\. This helps to ensure the security of the account’s billing data\. This bucket policy allows AWS \(`"Effect": "Allow"`\) to check which account owns the bucket \(`"Action": ["s3:GetBucketAcl", "s3:GetBucketPolicy"`\)\.
+ To deliver reports to your bucket, AWS needs write permissions for that bucket\. To do this, the bucket policy grants \(`"Effect": "Allow"`\) the AWS Cost and Usage Reports service \(`"Service": "billingreports.amazonaws.com"`\) permission to deliver \(`"Action": "s3:PutObject"`\) reports to the bucket you own \(`"Resource": "arn:aws:s3:::DOC-EXAMPLE-BUCKET/*"`\)\.

  This bucket policy does not give AWS permissions to read or delete any objects in your bucket, including the Cost and Usage Reports after they’ve been delivered\.
+ To ensure the bucket owner can access these reports, AWS further applies a `BucketOwnerFullControl` ACL to the reports when delivering them\. By default, Amazon S3 objects such as these reports can only be read by the user or service principal who wrote them\. To provide you or the bucket owner with permission to read the reports AWS must apply the `BucketOwnerFullControl` ACL\. The ACL grants the bucket owner `Permission.FullControl` for these reports\.

If you see an **Invalid bucket** error in your billing console for Cost and Usage Report, you should verify that this policy and bucket ownership haven’t changed after report setup\.