# View Monthly Spend by Service
- What are your top 3 services by cost?
  - EC2-Instances, Elastic Load Balancing, VPC

- Which service has grown the most month-over-month?
  - EC2-Instances, Elastic Load Balancing, VPC

- Are there any unusual spikes?
  - No

---
# Analyze Daily EC2 Costs
- Which instance types cost the most?
  - t3.micro
- Are there weekend patterns (costs drop on weekends)?
  - yes because i destroyed EC2s
- Any unusual daily spikes?
  - No

  ---
# Generate Cost Forecast
- What is the forecasted cost for next month?
  - 15.60$
- Is it within your budget?
  - yes
- What is the uncertainty range?
  - The uncertainty range is represented by the blue shaded region labeled as the 80% prediction interval. It starts roughly between -$0.50 and +$1.50 on Sep 01 and expands to about -$2.50 to +$3.50 by Nov 30.
---
#  Identify Data Transfer Costs
- Which services have high data transfer?
  - EC2
- Is data transfer growing?
  - No
- Does it represent >10% of costs? (may need optimization)
  - No
---
## AWS Cost Analysis - [18.08.2026]

## Executive Summary
- **Total Spend (Last Month):** $15.60
- **Change vs Previous Month:** -X% (Decreased due to destroying EC2 instances over weekends)
- **Top 3 Services:** EC2-Instances, Elastic Load Balancing, VPC
- **Forecast Next Month:** $15.60

## Key Findings
1. **Top Cost Drivers:** EC2-Instances, Elastic Load Balancing, and VPC account for the majority of the monthly cloud spend, with `t3.micro` being the highest-cost instance type.
2. **Weekend Cost Reduction:** Daily EC2 costs drop significantly on weekends due to active termination/destruction of EC2 instances.
3. **Data Transfer & Spikes:** Data transfer costs are driven primarily by EC2 but do not exceed 10% of total costs. No unusual cost or daily spikes were observed.

## Optimization Opportunities
1. **Automate Weekend EC2 Shutdowns:** Instead of manually destroying instances, implement auto-scaling or schedule-based start/stop scripts for `t3.micro` instances to consistently lower weekend spend.
2. **Review ELB & VPC Idle Resources:** Evaluate Elastic Load Balancing and VPC endpoints/NAT Gateways to ensure no unused idle resources are incurring fixed hourly charges.

## Screenshots
- See forecast-screenshot.png
- See service-breakdown-screenshot.png
