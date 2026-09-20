# Supply Chain Delivery Performance and Delay-Risk Analysis

## Overview

This project analyzes historical supply-chain shipment data to evaluate delivery performance, identify delay-risk exposure, and support operational prioritization across countries, vendors, and shipment complexity levels.

The original dataset is recorded at line-item level. To produce reliable delivery KPIs, the analysis consolidates line items into delivery events.

## Business Objective

Analyze historical supply-chain delivery records to identify delivery delays, quantify their operational and financial impact, and prioritize countries, vendors, and high-risk delivery events for corrective action.

## Key Questions

1. What is the overall On-Time Delivery performance?
2. Which countries have the highest delay rates, cumulative late days, and shipment-value exposure?
3. Which vendors contribute most to delivery-delay impact and reliability risk?
4. Are multi-site delivery events associated with increased late-delivery risk?
5. What operational actions should be prioritized to reduce delay exposure?

## Tools

- Python
- pandas
- Matplotlib
- Seaborn
- Jupyter Notebook
- Data cleaning and KPI design
- Supply chain and operational analytics

## Dataset

The dataset contains historical commodity-shipment records for anti-retroviral treatments and rapid test kits delivered to PEPFAR-supported countries.

Source: [Kaggle – Supply Chain Shipment Pricing Data](https://www.kaggle.com/datasets/divyeshardeshana/supply-chain-shipment-pricing-data)

> This project uses historical publicly available data for educational and portfolio purposes only.

## Data Modeling

The original dataset contains:

- **10,324** line-item records
- **7,030** unique delivery notices
- **7,040** delivery events after accounting for delivery notices with more than one scheduled delivery date

A delivery event is defined as:

\[
\text{Delivery Event Key} =
\text{Delivery Notice} + \text{Scheduled Delivery Date}
\]

This prevents line-item duplication from inflating delivery-performance KPIs.

## Key Results

| KPI | Result |
|---|---:|
| Total Delivery Events | 7,040 |
| On-Time Deliveries | 6,233 |
| Late Deliveries | 807 |
| On-Time Delivery Rate | 88.5% |
| Late Delivery Rate | 11.5% |
| Total Late Days | 16,121 |
| Average Late Days per Late Delivery | 20.0 |
| Total Shipment Value | $1.63B |
| Late Shipment Value | $259.0M |
| Late Shipment Value Exposure | 15.9% |

## Key Findings

- **South Africa** had the highest cumulative delay impact, with 4,631 total late days.
- **Congo, DRC** showed high delivery-risk severity, with a 21.2% late-delivery rate and 46.9 average late days per late delivery.
- **Mozambique** had high late-shipment-value exposure, with 29.3% of shipment value associated with delayed deliveries.
- **SCMS from RDC** had the largest vendor delay impact by cumulative late days.
- **Aurobindo Pharma Limited** had the highest late-delivery rate among the analyzed higher-volume vendors.
- **Multi-site delivery events** had a higher late-delivery rate than single-site deliveries: 17.0% compared with 11.0%.
- Multi-site delivery events also had higher late value exposure: 20.0% compared with 14.0%.

## Recommendations

1. Prioritize root-cause analysis in South Africa, Congo, DRC, and Mozambique.
2. Review SCMS from RDC and Aurobindo Pharma Limited using vendor-performance management processes.
3. Flag multi-site deliveries as higher-risk events during planning and assign additional coordination time and schedule buffers.
4. Build an early-warning dashboard that monitors On-Time Delivery, late days, late shipment value, and delay-risk exposure.
5. Interpret country and vendor late-delivery rates together with delivery volume.

## Limitations

- Results represent historical data only and do not reflect current organizational performance.
- The analysis identifies associations, not causal relationships.
- A delivery event can include multiple manufacturing sites; delay responsibility should not be assigned to one site without an event-site model.
- Freight-cost and weight fields require additional cleaning before cost or weight analysis.
- Small samples can make percentage-based rankings unstable.

## Repository Structure

```text
.
├── README.md
├── requirements.txt
├── notebooks/
│   └── supply_chain_delivery_performance_analysis.ipynb
└── data/
    └── README.md
```

## Author

Einav Shechter  
Data Analyst | Power BI | SQL | Python | Supply Chain Analytics
