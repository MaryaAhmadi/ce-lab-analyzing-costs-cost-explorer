# AWS Cost Analysis

## Step 2 - Monthly Spend by Service

- Top 3 services: EC2-Instances ($36.29), VPC ($14.75), Tax ($12.64)
- Highest growth service: EC2 (sudden increase in March)
- Observations:
  - Significant spike in March 2026
  - No costs in previous months → indicates recent usage start

## Step 3 - Daily EC2 Analysis

- Most expensive instance type: t3.medium ($13.95), followed by t2.micro ($13.89)
- Weekend pattern: No clear weekend cost reduction pattern observed
- Daily anomalies:
  - Significant spike starting around March 20
  - Sudden increase in t3.medium usage indicates new instance or workload

## Step 4 - Tag-Based Cost Allocation

- No tag data available yet
- Reason:
  - Cost allocation tags are already configured on resources
  - Tags were recently activated in Billing
  - AWS requires up to 24 hours for tag data to appear in Cost Explorer

## Step 5 - Cost Forecast

- Forecast not available
- Reason:
  - Insufficient historical data (only one month of usage)
  - AWS Cost Explorer requires multiple months of data to generate forecasts

- Budget status: Cannot be determined due to lack of forecast

- Confidence range: Not available

- Note:
  - Forecast accuracy is limited when usage is new or inconsistent
  - Additional months of usage data are required for reliable predictions

## Step 6 - Data Transfer Analysis

- No data transfer costs observed ($0.00)
- Data transfer does not contribute to overall AWS spending
- Reason:
  - No significant external traffic or inter-region data transfer
  - Current usage is limited to basic services (e.g., EC2 without heavy network usage)


## Step 7 - Saved Reports

- Created and saved the following reports:
  - Monthly Spend by Service
  - Daily EC2 Costs

- These reports can be reused for regular cost monitoring and stakeholder reviews


# AWS Cost Analysis - March 2026

## Executive Summary
- **Total Spend (Last Month):** ~$79
- **Change vs Previous Month:** +100% (no previous usage)
- **Top 3 Services:** EC2-Instances ($36.29), VPC ($14.75), Tax ($12.64)
- **Forecast Next Month:** Not available (insufficient data)

## Key Findings
1. AWS usage started recently, with all costs occurring in March 2026
2. EC2 is the primary cost driver, mainly from t3.medium and t2.micro instances
3. No data transfer costs observed, indicating minimal network traffic

## Optimization Opportunities
1. Review EC2 instance usage (t3.medium, t2.micro) and stop unused instances to reduce costs
2. Consider using smaller instance types or scheduling instances to run only when needed
3. Implement proper tagging and monitoring to improve cost visibility

## Screenshots
- forecast-screenshot.png
- service-breakdown-screenshot.png
