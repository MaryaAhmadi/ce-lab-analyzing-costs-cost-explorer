# Lab M7.01 - Analyzing Costs with AWS Cost Explorer

**Repository:** https://github.com/MaryaAhmadi/ce-lab-analyzing-costs-cost-explorer.git

**Activity Type:** Individual  
**Estimated Time:** 45-60 minutes

## Overview
In this lab, I explored AWS Cost Explorer to analyze cloud spending, identify cost drivers, and generate insights for financial decision-making. The goal was to simulate a FinOps scenario and provide answers to key business questions about cost trends and optimization opportunities.

## What I Did
Navigated AWS Cost Explorer interface
Created custom reports grouped by service and instance type
Analyzed monthly and daily cost trends
Attempted tag-based cost allocation
Investigated data transfer costs
Attempted to generate cost forecast
Saved reusable reports for future analysis

## Key Findings
💰 Top 3 Services by Cost
EC2-Instances → $36.29
VPC → $14.75
Tax → $12.64

## 📈 Cost Trend
All AWS usage started in March 2026
No spending in previous months → indicates new environment
Significant cost spike observed in March

## 🖥️ EC2 Usage Insights
Most expensive instance types:
t3.medium ($13.95)
t2.micro ($13.89)
No clear weekend usage pattern
Sudden increase in EC2 usage after March 20

## 🌐 Data Transfer
No data transfer costs observed ($0.00)
Indicates minimal external traffic or networking usage

## 🏷️ Tag-Based Allocation
Tags are configured on resources
However, data is not yet visible in Cost Explorer
AWS requires up to 24 hours after activation

## 🔮 Cost Forecast
Forecast not available
Reason: insufficient historical data (only one month of usage)

## Saved Reports
The following reports were created and saved for reuse:
Monthly Spend by Service
Daily EC2 Costs
These reports can be used for ongoing monitoring and stakeholder reporting.

## Optimization Opportunities
Review EC2 usage and stop unused instances
Consider smaller instance types to reduce compute cost
Implement scheduling (turn off instances when not needed)
Improve tagging strategy for better cost visibility
Monitor future data transfer as system scales

## Screenshots
forecast-screenshot.png
service-breakdown-screenshot.png

## Learning Reflection

1. Biggest cost surprise
The most surprising insight was that EC2 instances quickly became the main cost driver even with relatively small usage.

2. Most useful report
The Daily EC2 Cost report is the most useful because it reveals usage patterns and spikes clearly.

3. Explaining forecast to stakeholders
Since there is not enough historical data, I would explain that forecasting is currently unreliable and will improve over time as more usage data is collected.

4. Optimization opportunities identified
Reducing EC2 usage
Rightsizing instances
Scheduling workloads
Improving cost visibility through tagging

## Conclusion
This lab demonstrated how AWS Cost Explorer can be used to analyze spending, identify cost drivers, and support financial decision-making. Even with limited data, valuable insights can be extracted to guide optimization strategies.

## Repository Structure
cost-analysis.md → Detailed analysis
forecast-screenshot.png → Forecast attempt
service-breakdown-screenshot.png → Cost by service
README.md → Summary and explanation



## Step-by-Step Instructions

### Step 1: Enable Cost Explorer

1. AWS Console → Billing Dashboard
2. Left menu → Cost Explorer
3. If not enabled, click "Enable Cost Explorer" (takes 24 hours for data)
4. Once enabled, you'll see the main Cost Explorer interface

### Step 2: View Monthly Spend by Service

**Create your first report:**

1. In Cost Explorer, set:
   - **Time range:** Last 6 months
   - **Granularity:** Monthly
   - **Group by:** Service
   - **Show:** Cost (unblended)

2. Examine the stacked bar chart

3. **Questions to answer:**
   - What are your top 3 services by cost?
   - Which service has grown the most month-over-month?
   - Are there any unusual spikes?

4. **Document findings** in a file called `cost-analysis.md`

### Step 3: Analyze Daily EC2 Costs

1. Click "New report" or adjust current view:
   - **Time range:** Last 30 days
   - **Granularity:** Daily
   - **Filter:** Service = EC2
   - **Group by:** Instance Type

2. Examine the daily trend

3. **Questions to answer:**
   - Which instance types cost the most?
   - Are there weekend patterns (costs drop on weekends)?
   - Any unusual daily spikes?

4. Document in `cost-analysis.md`

### Step 4: Tag-Based Cost Allocation

**NOTE:** This requires cost allocation tags to be activated and resources to be tagged. If you don't have tags yet, skip to Step 5.

1. Create new report:
   - **Time range:** Current month
   - **Granularity:** Monthly
   - **Group by:** Tag (select Environment or Owner)
   - **Show:** Cost

2. If no data appears:
   - Tags may not be activated (Billing → Cost Allocation Tags)
   - Resources may not be tagged yet

3. If data appears:
   - Which environment (prod/dev/staging) costs most?
   - Document in `cost-analysis.md`

### Step 5: Generate Cost Forecast

1. In Cost Explorer:
   - **Time range:** Next 3 months
   - Leave other settings as default

2. Cost Explorer shows:
   - Forecasted monthly costs
   - 80% confidence interval (range)
   - Based on historical trends

3. **Questions to answer:**
   - What is the forecasted cost for next month?
   - Is it within your budget?
   - What is the uncertainty range?

4. Take a screenshot and save as `forecast-screenshot.png`

### Step 6: Identify Data Transfer Costs

1. Create new report:
   - **Time range:** Last 3 months
   - **Filter:** Usage Type contains "DataTransfer"
   - **Group by:** Service
   - **Granularity:** Monthly

2. Analyze data transfer patterns:
   - Which services have high data transfer?
   - Is data transfer growing?
   - Does it represent >10% of costs? (may need optimization)

3. Document findings in `cost-analysis.md`

### Step 7: Save Custom Reports

1. After creating a useful report, click "Save as..."
2. Name it descriptively (e.g., "EC2 by Instance Type - Monthly")
3. Save at least 2 reports:
   - "Monthly Spend by Service"
   - "Daily EC2 Costs"

4. Access saved reports from "Saved reports" tab

### Step 8: Create Executive Summary

In your `cost-analysis.md`, create an executive summary:

```markdown
# AWS Cost Analysis - [Date]

## Executive Summary
- **Total Spend (Last Month):** $X,XXX
- **Change vs Previous Month:** +X% or -X%
- **Top 3 Services:** EC2 ($X), S3 ($X), RDS ($X)
- **Forecast Next Month:** $X,XXX

## Key Findings
1. [Finding 1 with data]
2. [Finding 2 with data]
3. [Finding 3 with data]

## Optimization Opportunities
1. [Opportunity 1 with estimated savings]
2. [Opportunity 2 with estimated savings]

## Screenshots
- See forecast-screenshot.png
- See service-breakdown-screenshot.png
```


## Troubleshooting

**Cost Explorer not available:**
- Enable in Billing Dashboard (takes 24 hours)
- Check IAM permissions (need Cost Explorer access)

**No data showing:**
- Cost Explorer shows data from when it was enabled
- New accounts need 24 hours of usage
- Check selected time range

**Tags don't appear:**
- Cost allocation tags must be activated (Billing → Cost Allocation Tags)
- Takes 24 hours after activation
- Resources must be tagged before data appears

**Forecast seems wrong:**
- Forecasts based on historical patterns
- New services or major changes reduce accuracy
- Compare to business growth plans

## Submission Status

✅Cost Explorer accessed

✅Monthly service report created

✅Top 3 services identified

✅Daily EC2 analysis completed
✅
Tag-based allocation attempted

✅Forecast attempted (not available due to data limits)

✅Data transfer analyzed

✅Reports saved

✅Documentation completed



## Additional Resources

- [AWS Cost Explorer User Guide](https://docs.aws.amazon.com/cost-management/latest/userguide/ce-what-is.html)
- [AWS Cost Management Blog](https://aws.amazon.com/blogs/aws-cost-management/)

