# 1322 Signal Observatory

Public, machine-readable operating profiles for 1322's real-time social monitoring service: X (Twitter) typically 150-250ms, selected X Ultimate accounts around 100ms average, Instagram around 350ms median, Truth Social 150-250ms typical, and dedicated @realDonaldTrump / @WhiteHouse priority delivery around 50ms average. Maintained by the 1322 team; these are typical operating figures for selected product profiles, not an SLA, and the website's moving panel is a synthetic, privacy-safe replay, not live telemetry.

| Lane | Published operating figure | Scope |
| --- | --- | --- |
| X Standard | 150-250 ms typical | Standard monitored-account X delivery |
| X Ultimate | Around 100 ms average | Selected manually provisioned accounts |
| Instagram Standard | ~350 ms median | Tracked public Instagram accounts: posts, Stories, Reels and carousels |
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

## Related

- [1322-benchmark](https://github.com/SisoSol/1322-benchmark) - vendor-neutral CLI to measure these figures yourself
- [1322-client](https://github.com/SisoSol/1322-client) - TypeScript/JavaScript client for the feeds
- [1322-python](https://github.com/SisoSol/1322-python) - async Python client for the feeds
- [SisoSol](https://github.com/SisoSol) - all 1322 example repos
