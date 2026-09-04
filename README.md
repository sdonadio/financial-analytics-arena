# Financial Analytics Arena

An interactive companion for a 10-week course on financial analytics. Eleven
pages — a course map plus one page per week — each built around live, clickable
widgets rather than static slides: a tearsheet whose six panels re-compute from
one seeded return series, a corporate-action animator that pulls the raw close
away from the total return, a look-ahead join you can switch on to manufacture
a Sharpe of 6, a survivorship simulator that prices the bias in basis points, a
CAPM line you drag by hand, a hundred noise strategies of which five come back
"significant", and an efficient frontier that wobbles when you resample it.

The thesis of the course is that a financial number is only as good as the
decision it can survive. Prices become returns, returns become exposures,
exposures become weights, weights become risk, and every step is a place the
answer can be quietly wrong in a way no later step can detect. Ten weeks build
that one pipeline — ingest, model, optimise, stress, backtest, attribute — on
free public data, then point it at a live market.

| Week | Topic |
|------|-------|
| 1 | Financial Data & Returns |
| 2 | Factor Models & Cross-Sectional Regression |
| 3 | Portfolio Analytics & Optimisation |
| 4 | Risk Analytics |
| 5 | Rates, Inflation & the Macro Panel |
| 6 | Derivatives Analytics |
| 7 | Backtesting & Performance Attribution |
| 8 | Machine Learning for Finance |
| 9 | Market Microstructure & Execution Analytics |
| 10 | Review Day & Final |

Nothing is thrown away: the return panel built in week 1 is the substrate for
weeks 2, 3, 4 and 8; week 4 stresses the week-3 portfolio; weeks 8 and 10
report through the week-7 backtest harness; and weeks 9–10 point the whole
stack at a live venue and then measure, from the tape, what execution actually
cost.

The pages carry no course code, no institutional identity and no prerequisites
beyond comfort with pandas. Every dataset the course uses is free and public —
Yahoo Finance, FRED, the Ken French library, the SEC's XBRL API — plus the
class's own session recordings.

## Self-contained static HTML

Every page is a single `.html` file with exactly one inline `<style>` block and
one inline `<script>` block. There are no images, no build step, no package
manifest, no CDN and no external requests of any kind — the only outbound links
are to this repository, to the AlgoArena starter template, and to the three
sibling sites. All diagrams are inline SVG drawn by the page's own script. Each
page shares one byte-identical CSS custom-property palette, so re-theming the
site means editing the `:root` block.

Every price path, return panel, covariance matrix and t-statistic on the site is
generated from a seeded linear-congruential generator, so the same slider
always produces the same market and the numbers can be argued with.

## Sibling sites

Same shape, same contract, different subject:

- [Financial Markets Arena](https://sdonadio.github.io/financial-markets-arena/) — the finance primer, and the prerequisite reading for week 1
- [Systematic Trading Arena](https://sdonadio.github.io/systematic-trading-arena/) — ten weeks building the machinery this course analyses
- [Computer Architecture Arena](https://sdonadio.github.io/computer-architecture-arena/) — the machine your vectorised pandas actually runs on

The code the arena weeks refer to is **AlgoArena**, a Python
trading-competition platform. The public starter repo is
[algoarena-team-template](https://github.com/sdonadio/algoarena-team-template).

## Run it locally

```sh
git clone https://github.com/sdonadio/financial-analytics-arena
cd financial-analytics-arena
python3 -m http.server
```

Then open <http://localhost:8000/>.

Opening `index.html` directly from the filesystem also works, since nothing is
fetched over the network.

## Deploying

The site is plain static files, so GitHub Pages serves it as-is from the
repository root. `.nojekyll` is present so Pages skips Jekyll processing.

## Browser support

Any current browser. The pages use CSS custom properties, CSS grid, inline SVG
and ES5-compatible scripts, and honour `prefers-reduced-motion`. Layout
collapses to a single column below 720px.

## Licence

Content © the author, all rights reserved.
