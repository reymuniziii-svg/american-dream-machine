# The American Dream Machine

**Does your zip code determine your destiny?**

Interactive visualization exploring how childhood neighborhoods shape adult economic outcomes across 72,000 US neighborhoods.

## Live Demo

[View the visualization](https://reymuniziii-svg.github.io/american-dream-machine/scrollytelling.html)

## Features

- **Scrollytelling Narrative** — 8-step guided story revealing mobility patterns
- **Interactive Choropleth** — deck.gl-powered map of 3,000+ US counties
- **Demographic Toggle** — See how outcomes differ by race/ethnicity
- **Find Your Neighborhood** — Geolocation-powered neighborhood lookup
- **Animated Counters** — Editorial-quality statistics with smooth animations
- **Keyboard Navigation** — Arrow keys and number keys for accessibility

## The Story

The visualization reveals:

1. **The Rural Advantage** — Highest mobility is in rural Great Plains
2. **The Urban Challenge** — Major cities show limited mobility
3. **The Hyperlocal Reality** — Outcomes vary dramatically within cities
4. **The Demographic Divide** — Same place, different outcomes by race

## Data Source

[Opportunity Atlas](https://opportunityinsights.org/data/) — Census Bureau + Opportunity Insights

- 20 million children tracked from birth (1978-1983) to age 35
- 72,000 Census tracts analyzed
- Outcomes: household income, college attendance, incarceration

## Tech Stack

- [deck.gl](https://deck.gl) — WebGL-powered map layers
- [MapLibre GL JS](https://maplibre.org) — Free map rendering
- [D3.js v7](https://d3js.org) — Data visualization
- [Scrollama](https://github.com/russellgoldenberg/scrollama) — Scroll-triggered events

## Files

- `scrollytelling.html` — Main visualization (self-contained)
- `county_mobility.json` — County-level mobility data
- `summary.json` — National statistics
- `us-counties.json` — US county boundaries (GeoJSON)

## Local Development

```bash
cd ~/.claude/visualizations/mobility
python3 -m http.server 8080
# Open http://localhost:8080/scrollytelling.html
```

## Credits

Created by Rey Muniz using data from Raj Chetty's Opportunity Insights project.

## License

MIT
