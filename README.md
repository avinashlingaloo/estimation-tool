# est.

A point-based feature estimation tool for software teams. Single HTML file, no dependencies, no build step.

**[Try it live](https://avinashlingaloo.github.io/estimation-tool/)** | [Read the philosophy behind it](https://www.seangoedecke.com/how-i-estimate-work/)

## Why this exists

Most estimation tools ask "how long will this take?" — the wrong question. Unknown work dominates software projects, so estimation should focus on **unknowns, risk surfaces, and delivery approaches** rather than precise hour counts.

This tool is inspired by Sean Goedecke's article [How I Estimate Work](https://www.seangoedecke.com/how-i-estimate-work/), which argues that estimates are political tools and should present multiple delivery options with explicit tradeoffs.

## How it works

Score a feature across 5 dimensions using a modified Fibonacci scale (1-2-3-5-8-13):

| Dimension | What it measures | Weight |
|---|---|---|
| **Complexity** | Architectural complexity of the work | 1x |
| **Unknowns** | Unfamiliar code, no prior art, "dark forests" | **2x** |
| **Dependencies** | External blockers, other teams, APIs, approvals | 1x |
| **Risk** | Blast radius if something goes wrong | 1x |
| **Effort** | Raw volume of known work | 1x |

Unknowns are weighted 2x because they're the primary source of schedule variance.

The weighted total maps to a risk classification:

- **1-15** — Low risk. Straightforward, high confidence.
- **16-30** — Medium risk. Some unknowns, plan for contingency.
- **31-45** — High risk. Significant unknowns, multiple approaches needed.
- **46+** — Very high risk. Dark forest territory, scope negotiation required.

## Features

- **Approach builder** — Define up to 3 delivery approaches with adjusted scores and tradeoffs
- **Quick mode** — Stripped-down UI for fast gut-check estimates in meetings
- **Copy to clipboard** — Markdown output for Slack, Jira, Notion, or PR descriptions
- **History** — Auto-saves to localStorage, reload and edit past estimations
- **Requestor context** — Track the political context (executive priority, team initiative, etc.)
- **Zero dependencies** — Single HTML file, works offline, no server needed

## Usage

Open `index.html` in a browser. That's it.

```bash
# or serve it locally
npx serve .
```

## License

MIT
