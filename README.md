# threat-feed

Threat indicators published automatically by the Takedown Orchestrator, a research project
built at the tokens& Cyberdefense Hackathon in San Francisco on 9 October 2026.

| File | Use |
|---|---|
| [`blocklist.txt`](blocklist.txt) | One domain per line, for DNS blockers and browser filter lists |
| [`hosts.txt`](hosts.txt) | The same domains in hosts-file format |
| [`feed.json`](feed.json) | Every indicator with confidence, timestamps, status and evidence hash |
| [`incidents/`](incidents) | One page and one evidence bundle per incident |

Subscribe with the raw URL:

```
https://raw.githubusercontent.com/OutBlade/threat-feed/main/blocklist.txt
```

## How entries get here and how they leave

An entry is added when the pipeline's verdict stage flags a URL with enough confidence. The
entry is marked resolved and leaves the blocklist once two consecutive checks find the target
offline. Bad URLs on large shared platforms are listed in `feed.json` as single URLs and never
as blocked domains.

Each incident carries a SHA-256 hash of its evidence bundle. The same hash is quoted in every
abuse report sent for that incident, so a report can be checked against what is published here.
Incident pages show URLs defanged (`hxxp`, `[.]`).

## Limits

This is research output from a one-day project. It is not a vetted commercial feed. If a
domain is listed here by mistake, open an issue and it will be removed.
