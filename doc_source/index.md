#  User Guide

-----
*****Copyright &copy; Amazon Web Services, Inc. and/or its affiliates. All rights reserved.*****

-----
Amazon's trademarks and trade dress may not be used in 
     connection with any product or service that is not Amazon's, 
     in any manner that is likely to cause confusion among customers, 
     or in any manner that disparages or discredits Amazon. All other 
     trademarks not owned by Amazon are the property of their respective
     owners, who may or may not be affiliated with, connected to, or 
     sponsored by Amazon.

-----
## Contents
+ [What are AWS Cost and Usage Reports?](what-is-cur.md)
+ [Creating Cost and Usage Reports](creating-cur.md)
   + [Setting up an Amazon S3 bucket for Cost and Usage Reports](cur-s3.md)
   + [Creating Cost and Usage Reports](cur-create.md)
+ [Managing your Cost and Usage Reports](managing-cur.md)
   + [Viewing your Cost and Usage Reports details](view-cur.md)
   + [Accessing your Cost and Usage Reports in Amazon S3](access-cur-s3.md)
   + [Editing your Cost and Usage Reports configuration](edit-cur.md)
+ [Querying Cost and Usage Reports using Amazon Athena](cur-query-athena.md)
   + [Setting up Athena using AWS CloudFormation templates](use-athena-cf.md)
   + [Setting up Athena manually](cur-ate-manual.md)
      + [Creating an Athena table](create-manual-table.md)
      + [Creating a Cost and Usage Reports status table](create-manual-cur-table.md)
      + [Uploading your report partitions](upload-report-partitions.md)
   + [Running Amazon Athena queries](cur-ate-run.md)
   + [Loading report data to other resources](cur-query-other.md)
+ [Data dictionary](data-dictionary.md)
   + [Identity details](identity-columns.md)
   + [Billing details](billing-columns.md)
   + [Line item details](Lineitem-columns.md)
   + [Reservation details](reservation-columns.md)
   + [Pricing details](pricing-columns.md)
   + [Product details](product-columns.md)
   + [Resource tags details](resource-tags-columns.md)
   + [Savings Plans details](savingsplans-columns.md)
   + [Cost Categories details](cost-categories-columns.md)
+ [Use cases](use-cases.md)
   + [Understanding Savings Plans](cur-sp.md)
   + [Understanding your reservations](understanding-ri.md)
      + [Understanding your reservation line items](regular-reserved-instances.md)
      + [Understanding your amortized reservation data](amortized-reservation.md)
      + [Monitoring your size flexible reservations](monitor-flexible-reservation.md)
      + [Monitoring your On-Demand capacity reservations](monitor-ondemand-reservations.md)
+ [Legacy reports](legacy-reports.md)
   + [Detailed Billing Reports](detailed-billing.md)
      + [Migrating from Detailed Billing Reports to Cost and Usage Reports](detailed-billing-migrate.md)
   + [Monthly Report](monthly-report.md)
   + [Monthly cost allocation](monthly-cost-allocation.md)
   + [AWS Usage Report](usage-report.md)
+ [Contacting customer support](billing-get-answers.md)
+ [Security in AWS Cost and Usage Reports](security.md)
+ [Quotas and restrictions](billing-cur-limits.md)
+ [Document history for AWS Cost and Usage Reports User Guide](doc-history.md)
+ [AWS glossary](glossary.md)