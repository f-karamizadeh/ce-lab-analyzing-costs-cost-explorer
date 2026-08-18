# Lab M7.01 - Analyzing Costs with AWS Cost Explorer

**Repository:** [https://github.com/cloud-engineering-bootcamp/ce-lab-analyzing-costs-cost-explorer](https://github.com/cloud-engineering-bootcamp/ce-lab-analyzing-costs-cost-explorer)

**Activity Type:** Individual  
**Estimated Time:** 45-60 minutes

## Learning Objectives

- [ ] Navigate AWS Cost Explorer interface
- [ ] Create custom cost reports with filtering and grouping
- [ ] Analyze spending trends and patterns
- [ ] Save and share cost reports
- [ ] Generate cost forecasts

## Prerequisites

- [ ] AWS account with Cost Explorer enabled
- [ ] At least 2-3 months of AWS usage (or access to sample data)
- [ ] Completed Module 7 Lesson 1 and 2

## Introduction

AWS Cost Explorer is your primary tool for understanding where money is being spent. In this lab, you'll explore your AWS costs, identify the biggest spenders, and create reports for different stakeholders.

## Scenario

You're the FinOps engineer for a growing startup. The CFO asks: "Which services cost the most?" and "Are we trending over budget?" You'll use Cost Explorer to answer these questions.

## Your Task

**What you'll create:**
- Multiple custom cost reports
- Service-level cost breakdown
- Tag-based cost allocation view
- Cost forecast for next month
- Saved reports for weekly reviews

**Success criteria:**
- [ ] Identified top 3 spending services
- [ ] Created report grouped by tags
- [ ] Generated accurate forecast
- [ ] Saved at least 2 custom reports
- [ ] Documented findings in GitHub repo

**Time limit:** 45-60 minutes

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

## Submission

Submit to GitHub repository with:
1. `cost-analysis.md` - Your analysis and findings
2. `forecast-screenshot.png` - Cost forecast screenshot
3. `service-breakdown-screenshot.png` - Top services screenshot
4. `README.md` - Description of your analysis process

## Verification Checklist

- [ ] Accessed Cost Explorer successfully
- [ ] Created report showing monthly spend by service
- [ ] Identified top 3 spending services
- [ ] Created daily EC2 cost view
- [ ] Attempted tag-based allocation (if tags available)
- [ ] Generated 3-month forecast
- [ ] Analyzed data transfer costs
- [ ] Saved at least 2 custom reports
- [ ] Created executive summary with findings
- [ ] Screenshots captured and saved
- [ ] All files committed to GitHub

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

## Bonus Challenges

**Bonus 1: Rightsizing Analysis**
Access Cost Explorer → Recommendations → Rightsizing
- Review recommendations
- Document top 3 opportunities
- Calculate total potential savings

**Bonus 2: Reserved Instance Recommendations**
Cost Explorer → Recommendations → Reserved Instances
- Review RI purchase recommendations
- Document potential savings
- Calculate break-even point

**Bonus 3: Cost Anomaly Investigation**
If you have Cost Anomaly Detection enabled:
- Review recent anomalies
- Investigate root cause
- Document findings

## Learning Reflection

After completing this lab, answer:
1. What was your biggest cost surprise?
2. Which report would be most useful for your team?
3. How would you explain the forecast to non-technical stakeholders?
4. What optimization opportunities did you identify?

## Additional Resources

- [AWS Cost Explorer User Guide](https://docs.aws.amazon.com/cost-management/latest/userguide/ce-what-is.html)
- [AWS Cost Management Blog](https://aws.amazon.com/blogs/aws-cost-management/)

**Good luck! 🚀**
