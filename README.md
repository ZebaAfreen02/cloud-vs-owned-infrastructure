# Cloud vs. Owned Infrastructure
### A Comparative Cost and Scaling Analysis of Web-Service Deployment Models

A research-driven comparative study evaluating when organizations should rent cloud computing resources, invest in owned infrastructure, or adopt a hybrid deployment strategy.

Using **Shopify** and **Netflix** as contrasting case studies, this project models infrastructure costs across different workload patterns and analyzes how demand variability, growth, and hardware economics influence deployment decisions.

## Research Question

**When is renting cloud infrastructure more cost-effective than owning and operating physical servers?**

Rather than assuming one deployment model is universally better, the study examines how the answer changes across workload types and operational scales.

## Case Studies

| Characteristic | Shopify | Netflix |
|---|---|---|
| Industry | E-commerce | Video streaming |
| Modeled baseline | ~20 application instances | ~2,400 origin-tier instances |
| Representative demand spike | Black Friday/Cyber Monday | Major live-streaming events |
| Workload growth assumption | 22% annually | 10% annually |

The infrastructure sizes are **model-derived estimates**, not verified production server counts.

## Methodology

The study follows five stages:

1. **Workload profiling:** Estimate baseline capacity, peak demand, and growth assumptions for each platform.
2. **Cost modeling:** Compare cloud rental expenses against server ownership and operating costs.
3. **Scenario evaluation:** Calculate year-one and five-year costs for stable, spiky, and high-growth workloads.
4. **Sensitivity analysis:** Examine how changes in key assumptions affect the economic comparison.
5. **Decision-framework synthesis:** Translate the findings into practical deployment recommendations.

### Cloud Infrastructure Model

The cloud model considers:

- AWS EC2 compute using c5.4xlarge instances
- One-year reserved and on-demand pricing
- Storage and data transfer
- Application load balancing
- Elastic capacity during traffic spikes

### Owned Infrastructure Model

The ownership model considers:

- Hardware acquisition at an assumed **$6,000 per server**
- Four-year hardware lifespan
- Power consumption and data-center efficiency
- Colocation expenses
- Hardware maintenance
- Additional capacity required to accommodate peak workloads

The baseline operating-cost assumption is approximately **$1,300 per server annually**.

## Workload Scenarios

### Stable Demand

Predictable workloads with relatively consistent infrastructure requirements.

Under the model assumptions, owned infrastructure is generally more economical because hardware capacity can be utilized consistently.

### Spiky Demand

Workloads experiencing short periods of substantially higher traffic.

Cloud infrastructure benefits from temporary capacity expansion, while owned infrastructure must provision enough hardware to handle peak demand throughout the year.

### High-Growth Demand

Workloads requiring progressively more capacity over a five-year horizon.

Ownership can offer lower modeled infrastructure costs, while cloud infrastructure provides greater flexibility when growth forecasts are uncertain.

## Key Results

### Shopify — Five-Year Infrastructure Costs

| Scenario | Cloud | Owned | Lower-cost option |
|---|---:|---:|---|
| Stable | $435,060 | $280,000 | Owned |
| Spiky | $617,816 | $1,008,000 | Cloud |
| High growth | $1,340,722 | $500,100 | Owned |

### Netflix — Five-Year Infrastructure Costs

| Scenario | Cloud | Owned | Lower-cost option |
|---|---:|---:|---|
| Stable | $52.58M | $33.60M | Owned |
| Spiky | $57.64M | $100.80M | Cloud |
| High growth | $70.56M | $41.00M | Owned |

*All results are modeled estimates based on the assumptions described in the report. They are not actual infrastructure expenditures reported by Shopify or Netflix.*

## Key Findings

**1. Workload shape matters more than company size.**

Despite the substantial difference in modeled infrastructure scale, Shopify and Netflix exhibit the same preferred deployment strategy across the three workload scenarios.

**2. Cloud infrastructure is advantageous for bursty demand.**

Elastic scaling avoids the expense of permanently provisioning hardware for short-lived traffic peaks.

**3. Ownership can reduce costs for predictable workloads.**

Consistent utilization allows organizations to spread hardware acquisition and operating costs across sustained demand.

**4. Hardware pricing strongly affects the outcome.**

The analysis estimates a break-even hardware cost of approximately **$12,200–$12,300 per server** for the stable-workload comparison.

**5. Hybrid infrastructure offers a practical compromise.**

Maintaining predictable baseline capacity while renting additional resources during traffic spikes can combine cost efficiency with flexibility.

## Sensitivity Analysis

The study evaluates the effect of changes in:

- Cloud reserved-instance pricing
- Hardware acquisition cost
- Hardware lifespan
- Workload growth rate
- Peak-to-baseline traffic multiplier

The analysis highlights how higher traffic spikes disproportionately increase the cost of owned infrastructure, while sustained growth can significantly increase cumulative cloud expenditure.

## Deployment Decision Framework

| Workload characteristic | Suggested deployment model |
|---|---|
| Stable, predictable demand | Owned infrastructure, when hardware economics are favorable |
| Large, short-duration traffic spikes | Cloud |
| High growth with predictable demand | Owned infrastructure on modeled infrastructure cost |
| High growth with uncertain forecasts | Cloud |
| Large-scale workloads with variable demand | Hybrid |
| Early-stage systems with uncertain capacity needs | Cloud |
| Workloads with specific regulatory constraints | Evaluate owned or private-cloud options |

These recommendations are conditional on the assumptions, costs, and operational requirements of the organization.

## Scope and Limitations

The analysis focuses primarily on **infrastructure cost**, rather than a complete total-cost-of-ownership assessment.

The report does not fully model:

- Staffing and operational labor costs
- Performance and latency differences
- Detailed reliability and SLA comparisons
- Sustainability and carbon impact
- All infrastructure tiers, such as databases, caches, and content delivery networks

The findings should therefore be interpreted as a comparative cost-modeling exercise rather than universal recommendations for production infrastructure.

## Full Research Report

The complete report contains the detailed calculations, assumptions, cost comparisons, charts, sensitivity analysis, references, and decision framework.

**[Read the Full Research Report](RentVsOwnGroup8FinalReport%283%29.pdf)**

## Academic Context

Developed as a collaborative final project for **CS 553 — Design of Internet Services**, Rutgers University.

**Project team:**

- Sridevi Mudiyanur Ramamurthy
- Zeba Afreen
- Safa Akbar
- Ellysha Fatima
- Md Aqeed Safwaan

## Conclusion

The study demonstrates that infrastructure deployment decisions should be guided by workload behavior, economic assumptions, and operational flexibility rather than organizational scale alone.

For predictable demand, owned infrastructure can provide substantial cost savings. For highly variable workloads, cloud elasticity often outweighs the benefits of ownership. Hybrid approaches can offer a balance between the two.
