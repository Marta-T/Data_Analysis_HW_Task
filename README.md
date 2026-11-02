# Asset Performance Investigation – AlphaWind Park

## 1. Background

AlphaWind is a wind park consisting of **6 turbines**.

Over the last 7 days, we have observed inconsistencies between expected and actual energy production. Some production losses can be explained by known operational events, while others are not clearly documented.

Your main stakeholder for this investigation is the **Asset Supervisor** responsible for the park. They have strong engineering and operational knowledge of wind farm operations, but are not necessarily familiar with data analytics or modelling techniques.

We expect you to investigate the available data, identify the main drivers of production losses and develop an understanding of what happened during the period.

You are free to choose your analytical approach and tools. The important part is to arrive at meaningful conclusions that help the stakeholder understand the park's performance and identify where further operational attention may be needed.

## 2. Data Provided

You are given the following datasets:

| Dataset | Description | Granularity |
|---|---|---|
| `production.csv` | Energy production per turbine | 10 minutes |
| `weather.csv` | Wind speed measurements | Park level, 10 minutes |
| `stops_log.csv` | Operational stop and event records | Event level |
| `turbine_metadata.csv` | Turbine information and service history | Turbine level |

All datasets cover the same 7-day period.

## 3. Operational Context

Wind turbine production depends strongly on wind conditions, but actual production can also be affected by operational constraints.

The following operational event types are relevant:

| Code | Meaning | Scope |
|---|---|---|
| WND | Extreme wind conditions | Park level |
| GRD | Grid limitation | Park level |
| FLT | Technical turbine fault | Turbine level |
| MTN | Scheduled maintenance | Turbine level |

The stop log is not fully reliable. It may contain:

- Missing event end timestamps.
- Duplicate event records.
- Incorrect or extended event durations.
- Incomplete reporting of park-level events across individual turbines.

Some production losses may also have no corresponding operational event record.

Use your judgement when interpreting the operational records. Clearly explain any assumptions you make when handling incomplete, inconsistent or conflicting information.

## 4. Your Task

Investigate AlphaWind's performance during the 7-day period and identify the main drivers of energy production losses.

Structure your investigation around the following areas:

### 4.1. Park-Level Performance

Understand how the park performed as a whole.

Consider how production relates to wind conditions, whether actual production meets expectations, and when significant production losses occur.

### 4.2. Turbine-Level Performance

Compare the performance of individual turbines.

Look for differences in production and operational behaviour. Identify turbines that appear to perform differently and investigate potential reasons.

### 4.3. Data Quality and Operational Events

Evaluate how reliable the available data is for explaining production losses.

Investigate inconsistencies in the stop logs, consider how missing or incorrect event information could be handled, and identify production losses that cannot be explained by recorded events.

You do not need to investigate every issue in equal detail. Prioritise the findings that have the greatest impact on understanding park performance.

## 5. Expected Production and Energy Loss Estimation

Build a model or analytical baseline to estimate expected production based on wind conditions.

The approach is your choice. It could be based on a theoretical power curve, historical production patterns, statistical modelling or another reasonable method.

Use this baseline to:

1. Compare expected and actual production.
2. Identify periods of significant production losses.
3. Estimate energy losses by cause.
4. Distinguish explained losses from unexplained losses.

Provide a **park-level energy loss breakdown**:

| Cause | Estimated energy loss (kWh) |
|---|---:|
| Extreme wind conditions (WND) | |
| Grid limitation (GRD) | |
| Technical faults (FLT) | |
| Scheduled maintenance (MTN) | |
| Unexplained | |
| **Total** | |

Explain your attribution methodology and key assumptions, including how you avoid double-counting losses.

The estimates do not need to be perfectly accurate. We are interested in whether your methodology is reasonable, transparent and consistently applied.

## 6. Deliverables

### 1. Analysis

Provide your analysis in a format of your choice, for example:

- Python notebooks or scripts.
- SQL queries.
- Excel.
- Power BI.
- Other analytical tools.

The work should be reproducible, with sufficient documentation to understand your approach.

### 2. Stakeholder Brief (1–2 pages)

Summarise your:
- Overall park performance and key findings.
- Key turbine-level findings.
- Main operational and data quality issues.
- Estimated park-level energy loss breakdown.
- Assumptions and limitations.
- Recommended follow-up actions.

If some aspects of the investigation remain incomplete, or you identify improvements that would require additional time, include them in the brief under TODO section. Explain what remains to be done, why it matters and what you would prioritise next.

The summary should allow the Asset Supervisor to understand what happened, which issues matter most and where further operational attention may be needed.

### 3. Delivery

Submit your solution as a GitHub repository and share the repository URL with us.

You are free to organise the project structure as you see fit. The repository should contain the materials needed to understand and reproduce your analysis, including relevant code, notebooks and documentation.

Public and private repositories are both acceptable. If submitting a private repository, please ensure that the relevant reviewers have access.

## 7. What We Are Looking For

We are not looking for a perfect solution or a highly sophisticated forecasting model.

We are interested in your ability to:

- Structure an ambiguous operational problem.
- Understand and validate unfamiliar datasets.
- Identify patterns and anomalies in time-series data.
- Work with incomplete and inconsistent operational records.
- Build a reasonable expected-production baseline.
- Make transparent assumptions and avoid double-counting.
- Translate analytical findings into practical operational insights.
- Communicate conclusions clearly.

You are free to choose your tools, analytical methods and level of technical complexity. We value sound reasoning and useful conclusions over unnecessary complexity.

## 8. Expected Effort

Approximately **4–5 hours**.

You are not expected to investigate every possible aspect of the problem. Prioritise the work you consider most valuable within the available time.