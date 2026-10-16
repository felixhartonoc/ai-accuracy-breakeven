# AI Accuracy Break-Even

A single-file static calculator for the question that comes before every AI cost model:
**is the model accurate enough for automating to be cheaper than reviewing by hand?**

Enter four numbers -- daily volume, the cost of one wrong output, the cost of a human review,
and your measured accuracy -- and see the minimum accuracy automation has to clear.

Built for [ctaio.dev](https://ctaio.dev).

## Why

CTAIO's enterprise AI ROI playbook names five failure patterns. The fourth is *accuracy mismatch
against the required threshold* -- the failure where a model is good enough in a demo and not good
enough in production. The playbook describes the failure; this prices it.

## The calculation

- Break-even accuracy = `1 - (review cost / error cost)`
- No review = `1000 x (1 - accuracy) x error cost`
- Full review = `1000 x review cost`
- Targeted review = `1000 x error rate x review cost + 1000 x error rate x 0.1 x error cost`

Targeted review assumes a confidence signal exists and that reviewing the lowest-confidence tail
-- sized to the model's error rate -- catches 90% of errors. That assumption is stated in the tool
itself, not buried in the code.

## Running it

Open `index.html`. No build step, no dependencies, no network calls. Nothing you type leaves the
browser.

## Licence

MIT.
