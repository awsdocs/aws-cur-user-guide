# Monitoring your On\-Demand capacity reservations<a name="monitor-ondemand-reservations"></a>

Capacity reservations enable you to reserve capacity for your Amazon EC2 instances for any duration in a specific Availability Zone\. This enables you to create and manage capacity reservations separately from the billing discounts offered by Regional Reserved Instances \(RI\)\. To benefit from billing discounts, you can use Regional RIs in combination with capacity reservations\.

## Capacity reservation line items<a name="capacity-reservation-li"></a>

You can use some columns defined in the AWS CUR data dictionary to track your capacity reservations\. The following columns are also used for capacity reservations\.

This section defines these line items with supplementary definitions specific to capacity reservations\.

For more information about Cost and Usage Reports column descriptions, see [Line item details](Lineitem-columns.md)\.

A \| [B](#lcr-B) \| C \| D \| E \| F \| G \| H \| I \| J \| K \| L \| M \| N \| O \| P \| Q \| [R](#lcr-R) \| S \| T \| [U](#lcr-U) \| VWXYZ 

### B<a name="Lineitem-cr-details-B"></a>

#### lineItem/BlendedRate<a name="Lineitem-cr-details-B-BlendedRate"></a>

For capacity reservations with a **UsageType** of **Reservation** or **DedicatedRes**, the **BlendedRate** is `0`\. This is because the capacity reservation costs are associated with the instance that provides the capacity, instead of with the capacity reservation itself\. 

### R<a name="Lineitem-cr-details-R"></a>

#### lineItem/ResourceId<a name="Lineitem-cr-details-R-ResourceId"></a>

If you included `lineItem/ResourceId` when you created your Cost and Usage Reports, you can identify and track your capacity reservations using the **ResourceId** column\. The capacity reservation **ResourceId** is captured only for the **UnusedBox,** **UnusedDed**, **Reservation**, and **DedicatedRes** **UsageTypes**\.

Capacity reservations always include a `cr-` in their resource ID, and the resource ID has the following format:

```
arn:aws:ec2:<region>:<account id>:<capacity-reservation>/cr-0be443example1db6f
```

### U<a name="Lineitem-cr-details-U"></a>

#### lineItem/UnblendedCost<a name="Lineitem-cr-details-U-UnblendedCost"></a>

The `BlendedRate` multiplied by the `UsageAmount`\.

#### lineItem/UnblendedRate<a name="Lineitem-cr-details-U-UnblendedRate"></a>

For capacity reservations with a **UsageType** of **Reservation** or **DedicatedRes**, the **UnblendedRate** is `0`\. This is because the costs for capacity reservations are associated with the instance that provides the capacity, instead of with the capacity reservation itself\.

#### lineItem/UsageAmount<a name="Lineitem-cr-details-U-UsageAmount"></a>

How much of a capacity reservation you've used\. Each capacity reservation can have multiple slots for an hour, enabling you to run more than one instance that uses the reservation during an hour\. Therefore, it's possible to use more than one instance\-hour in an hour\. **UsageAmount** is calculated by multiplying the number of instance slots covered by the line item with the number of hours covered by the line item\.

#### lineItem/UsageType<a name="Lineitem-cr-details-U-UsageType"></a>

How much of a specific reservation you've used\. For Amazon EC2, the options are as follows:

##### lineItem/lineitemtype = BoxUsage<a name="Lineitem-cr-details-U-BoxUsage"></a>

For this `UsageType`, the `UsageAmount` column is the amount of instance\-hours of an instance you've used\.

For example, a report covers 1 hour and has a capacity reservation line item that can cover 10 instances\. If you use two instance\-slots during the time period covered by the report, the **BoxUsage** **UsageAmount** covers the number of instance hours that you reserved and used\. In this case, this is two \(the number of used instance slots\) multiplied by 1 hour \(the time covered by the report\) for a total of two\. For a report that covers 1 day, the **UsageAmount** is two multiplied by 24, for a total of 48\.

##### DedicatedRes<a name="Lineitem-cr-details-U-DedicatedRes"></a>

For a **UsageType** of **DedicatedRes**, the **UsageAmount** column describes how many instance\-hours of a dedicated capacity reservation you reserved\.

##### Reservation<a name="Lineitem-cr-details-U-Reservation"></a>

For a **UsageType** of **Reservation**, the **UsageAmount** column describes how many instance\-hours of a capacity reservation you reserved\.

For example, if a report covers one hour and has a capacity reservation line item that can cover 10 instances, the **Reservation** **UsageAmount** covers the number of instance slots that you reserved\. In this case, that's 10 \(the number of available instance slots\) multiplied by 1 hour \(the time covered by the report\) for a total of 10\. For a report that covers 1 day, the **UsageAmount** would be 10 multiplied by 24, for a total of 240\.

##### UnusedBox<a name="Lineitem-cr-details-U-UnusedBox"></a>

For a **UsageType** of **UnusedBox**, the **UsageAmount** column describes how many instance\-hours of a capacity reservation you reserved, but didn't use\.

For example, a report covers 1 hour and has a capacity reservation line item that can cover 10 instances\. If you didn't use eight instance\-slots during the time period covered by the report, the **UnusedBox** **UsageAmount** covers the number of instance hours that you reserved but didn't use\. In this case, that's eight \(the number of unused instance slots\) multiplied by 1 hour \(the time covered by the report\) for a total of eight\. For a report that covers 1 day, the **UsageAmount** is eight multiplied by 24, for a total of 192\.

##### UnusedDed<a name="Lineitem-cr-details-U-UnusedDed"></a>

For a **UsageType** of **UnusedDed**, the **UsageAmount** column describes how many instance\-hours of a dedicated capacity reservation that you reserved, but didn't use\.