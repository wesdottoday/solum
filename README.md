# Solum

*Latin: the living layer of soil where everything grows.*

Solum is an open-source project building an AI model for regenerative agriculture and soil health. The goal: help anyone in the world figure out what will grow best in the soil they have and what they can do to improve that soil for the future.

This project exists because one of the biggest issues we face is the destruction of our topsoil. Industrial monocropping is degrading the land that feeds us, and it's incredibly difficult to grow healthy food without healthy soil. Regenerative farming offers a better path, but doing it well requires deep, location-specific knowledge that's scattered across thousands of sources worldwide.

Solum brings that knowledge together. We're collecting high-quality public data globally (soil types, plant species, climate, ecosystems) and building interwoven relationships between micro-locations, soil composition, plant communities, and what they all need to thrive. The United States has the highest resolution coverage today, and we're actively working to improve resolution globally.

**This project is early.** We're in the data collection and pipeline phase. There's no trained model yet. If that excites you more than it discourages you, keep reading.

## Data Principles

Every piece of data in Solum's training corpus must pass a set of hard gates. No exceptions.

### What we use

- **Publicly licensed data only.** Public domain, CC0, CC-BY, CC-BY-SA, CC-BY-NC, and government open data. Every source is tagged with its license in our tracking database and must be explicitly approved before it can enter the processing pipeline.
- **Every source is listed.** We maintain a [complete catalog](DATA_SOURCES.md) of every dataset, its provider, license, and what it contains. Full attribution, always.
- **Verifiable data from trustworthy sources.** Government agencies, research institutions, universities, peer-reviewed journals, and established non-profits. We don't use data from entities actively contributing to the destruction of our land and ecosystems.

### What we don't use

- **Copyrighted material.** No books, paywalled journals, or proprietary datasets unless explicitly licensed for this use.
- **Unverifiable or unreliable data.** If we can't confirm where it came from and that it's accurate, it doesn't go in.
- **Extracted Indigenous knowledge.** Indigenous agricultural knowledge is among the most valuable ecological knowledge on Earth. We only use materials that have been explicitly published and shared by Indigenous organizations themselves. We do not scrape, decontextualize, or treat Indigenous communities as data sources. Where possible, we seek collaborative partnerships rather than one-way extraction.

### How we collect

We respect the systems that provide our data:

- **Rate limiting.** All collection scripts enforce delays between requests to minimize load on source servers.
- **Least-impact retrieval.** We use bulk downloads and official APIs where available rather than scraping. When scraping is necessary, we use the most efficient method that puts the least burden on the provider.
- **No probing.** We don't test rate limits or attempt to circumvent access controls.
- **Transparent identification.** Our scripts identify themselves as `Solum/1.0 (soil health research; https://github.com/wesdottoday/solum)` in all requests.
- **Open to feedback.** If you are a data provider and would like us to stop using your data, retrieve it differently, or have any other concerns, please reach out to wk@wes.today.

## Where We Are

Solum is in the **data collection and pipeline phase**. There is no trained model yet.

What exists today:

- **~61 GB of raw data** collected from 26 sources worldwide, covering soil composition, plant species, climate, land cover, biodiversity, historical agriculture research, and on-farm practitioner reports.
- **A working processing pipeline** that transforms raw data into training-ready documents (narrated soil profiles, geocoded research reports, and structured species data) with license gates enforced at every step.
- **Vertical slices proven** for multiple US states: end-to-end from raw download through processed training records, with audit reports confirming all data passes license and quality gates.

### Test Regions

We validate data depth and coverage against a set of test regions intentionally chosen to span climate zones, continents, and varying levels of data availability, not just places where we know we're strong:

| Region | Why | Climate Zone |
|--------|-----|-------------|
| **Worthington, OH, USA** | Project home base, deep US coverage | Humid continental |
| **Helsinki, Finland** | European coverage, very different climate from US baseline | Boreal / subarctic |
| **Tokyo, Japan** | East Asian coverage, personal connection to the region | Humid subtropical |
| **Nairobi, Kenya** | East African coverage, strong soil data (iSDA 30m) but limited practitioner knowledge | Tropical highland |
| **Mato Grosso, Brazil** | South American agricultural frontier, Cerrado biome | Tropical savanna |
| **Canterbury, New Zealand** | Southern hemisphere temperate, tests Oceania coverage | Maritime temperate |
| **Rajasthan, India** | Arid/semi-arid, a region we know we're weak in | Hot desert / semi-arid |

These test regions are a starting point. The long-term vision is **SolumBench**, a standalone evaluation suite (separate repository, coming soon) that will run as CI against a much larger set of zones covering every major climate region and most countries, producing coverage and depth reports automatically.

### Known Gaps

Healthy soil is not just minerals and chemistry. It's a living ecosystem, and our data doesn't yet reflect that fully. The biggest gaps we're actively working to fill:

- **Insects and pollinators.** Soil health depends on insects at every level, from earthworms and beetles breaking down organic matter to pollinators sustaining the plants that hold soil together. We don't have dedicated entomological datasets yet.
- **Animals and wildlife.** Grazing patterns, burrowing animals, bird-driven seed dispersal, and predator-prey dynamics all shape the land. We need wildlife interaction data.
- **Chemical contamination.** Pesticides, herbicides, PFAS, heavy metals, and industrial runoff have profound effects on soil biology and what can safely grow. We need contamination and remediation data.
- **Natural and man-made disasters.** Floods, fire, drought, oil spills, and industrial accidents reshape soil health in ways that persist for decades. Understanding disaster impact and recovery is critical for real-world advice.

These are all areas we will be actively correcting over the coming days.

## Contributing

Solum is not accepting code contributions at this time. The project is early enough that the technical direction is still taking shape.

What we do need:

- **Data source leads.** Know of a publicly licensed soil, climate, plant, or agriculture dataset we should be using, especially outside the US? See our [current source list](DATA_SOURCES.md) and open an issue or email wk@wes.today.
- **Domain expertise.** Soil scientists, agronomists, ecologists, and extension agents who can help us validate that our data is being used correctly and that the relationships we're building make sense.
- **Farmer and practitioner perspective.** If you grow food, at any scale, anywhere in the world, we want to hear what questions you'd ask this system. What would actually be useful to you? That input shapes everything.

If any of those describe you, please reach out. The best way is to [open an issue](https://github.com/wesdottoday/solum/issues) or email wk@wes.today.

## License

The Solum codebase is licensed under the [GNU Affero General Public License v3.0](LICENSE) (AGPL-3.0). This means you can use, modify, and distribute the code freely, but any derivative work, including network services built on it, must also be open source under the same terms.

When model weights are released, they will be licensed under [CC-BY-NC-SA-4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/) (Creative Commons Attribution-NonCommercial-ShareAlike). This ensures the model remains non-commercial and any derivatives are shared under the same terms, consistent with the licensing spirit of our training data.
