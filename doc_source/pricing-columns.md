# Pricing details<a name="pricing-columns"></a>

The pricing columns in AWS Cost and Usage Reports contain the prices for a line item\. The pricing columns are based off of the AWS Price List Service API\. AWS Price List Service API doesn't include Free Tier pricing, Spot Instances, products in AWS Marketplace, upfront annual subscription fees \(`Fee`\), and monthly recurring fees \(`RIFee`\)\. The columns include but are not limited to the following:

 A \| B \| C \| D \| E \| F \| G \| H \| I \| J \| K \| [L](#pr-L) \| M \| N \| O \| [P](#pr-P) \| Q \| [R](#pr-R) \| S \| [T](#pr-T) \| [U](#pr-U) \| VWXYZ 

## L<a name="pricing-details-L"></a>

### pricing/LeaseContractLength<a name="pricing-details-L-LeaseContractLength"></a>

The length of time that your RI is reserved for\.

## P<a name="pricing-details-P"></a>

### pricing/publicOnDemandCost<a name="pricing-details-P-publicOnDemandCost"></a>

The total cost for the line item based on public On\-Demand Instance rates\. If you have SKUs with multiple On\-Demand public costs, the equivalent cost for the highest tier is displayed\. For example, services offering free\-tiers or tiered pricing\.

### pricing/publicOnDemandRate<a name="pricing-details-P-publicOnDemandRate"></a>

The public On\-Demand Instance rate in this billing period for the specific line item of usage\. If you have SKUs with multiple On\-Demand public rates, the equivalent rate for the highest tier is displayed\. For example, services offering free\-tiers or tiered pricing\.

### pricing/PurchaseOption<a name="pricing-details-P-PurchaseOption"></a>

How you chose to pay for this line item\. Valid values are `All Upfront`, `Partial Upfront`, and `No Upfront`\.

## R<a name="pricing-details-R"></a>

### pricing/RateCode<a name="pricing-details-R-RateCode"></a>

A unique code for a product/ offer/ pricing\-tier combination\. The product and term combinations can have multiple price dimensions, such as a free tier, low\-use tier, and high\-use tier\.

### pricing/RateId<a name="pricing-details-R-RateId"></a>

The ID of the rate for a line item\.

## T<a name="pricing-details-T"></a>

### pricing/term<a name="pricing-details-T-term"></a>

Whether your AWS usage is Reserved or On\-Demand\.

## U<a name="pricing-details-U"></a>

### pricing/unit<a name="pricing-details-U-unit"></a>

The pricing unit that AWS used for calculating your usage cost\. For example, the pricing unit for Amazon EC2 instance usage is in hours\.