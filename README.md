# 1322 Signal Observatory

Public, machine-readable operating profiles for selected 1322 real-time monitoring lanes.

| Lane | Published operating figure | Scope |
| --- | --- | --- |
| X Standard | 150-250 ms typical | Standard monitored-account X delivery |
| X Ultimate | Around 100 ms average | Selected manually provisioned accounts |
| Truth Standard | 150-250 ms typical | Standard Truth Social delivery |
| Truth Priority | Around 50 ms average | Dedicated @realDonaldTrump and @WhiteHouse lanes |

These are typical operating figures, not an SLA. They describe selected 1322 product lanes and should not be generalized to every source, account, region, payload stage, or network path.

## Data and methodology

- Observatory and methodology: https://1322.io/speed
- JSON dataset: https://1322.io/speed/data
- CSV dataset: https://1322.io/speed/data?format=csv
- One-day evaluation: https://1322.io/trial

The animated panel on the Observatory is a deterministic, privacy-safe synthetic replay constrained to the published profiles. It is not live telemetry, contains no customer events, and is not connected to private backend infrastructure.

## Read the dataset

    curl -s https://1322.io/speed/data
    curl -s "https://1322.io/speed/data?format=csv"

The JSON response carries the disclosure flags alongside the claims:

- liveTelemetry: false
- replayIsSynthetic: true
- customerDataUsed: false

## How to evaluate a real-time feed

Measure the same event stage on both sides:

1. Record the source publication timestamp.
2. Record the provider detection timestamp, when available.
3. Record arrival at your consumer.
4. Keep region, account list, connection mode, and payload stage fixed.
5. Report sample count plus p50 and p90, not one best-case event.

A buyer should validate the product with their own accounts and consumer region. 1322 provides a one-day evaluation without a card for that purpose.

## Citation

When referencing these figures, link to https://1322.io/speed so readers can see the current scope and methodology. Independent replications are welcome, including results that are slower than the published figures when the method and sample are clear.