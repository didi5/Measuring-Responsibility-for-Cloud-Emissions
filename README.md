# Query-Level Carbon Attribution for Cloud Databases

> **Portfolio category:** Responsible Technology · Research & Academic Projects  
> **Status:** Research concept and literature-based design — not a runnable software prototype

This repository explores how the carbon emissions of shared cloud database infrastructure could be attributed more transparently at query level. The product vision is to make environmental impact visible enough for engineers to compare database execution strategies.

## Research problem

Cloud carbon accounting is often reported at infrastructure, tenant, or workload level. That makes it difficult to identify which individual queries create resource demand, contribute to peaks, or could be executed differently.

## Proposed approach

1. Measure query-level indicators such as CPU time, memory, and I/O.
2. Map execution time to location- and time-specific grid carbon intensity.
3. Apply a fair attribution model for shared and peak infrastructure.
4. Compare caching, materialized views, indexing, and temporal shifting.
5. Communicate trade-offs between performance, cost, freshness, and emissions.

## Research foundation

The concept builds on sustainable data-management coursework at the Hasso Plattner Institute and the Fair-CO₂ research direction. The repository also preserves related research material for study and discussion.

## What is — and is not — in this repository

- Included: research framing, conceptual architecture, questions, and source material.
- Not included: a verified carbon calculator, database integration, benchmark suite, API, or measured project results.
- Numerical examples must be treated as illustrations or literature-derived assumptions unless linked to a reproducible experiment.

## Potential engineering roadmap

- Create a reproducible PostgreSQL measurement pipeline
- Define system boundaries and allocation rules
- Integrate a documented carbon-intensity data source
- Validate formulas against real query traces
- Compare optimization strategies in controlled experiments
- Publish assumptions, uncertainty, and sensitivity analyses

## Academic transparency

This is a separate sustainable-computing research project and is not presented as Dilem Kaya's Digital Health master's thesis.

## Author

**Dilem Kaya — AI Engineer & AI Product Builder**  
Hasso Plattner Institute

- Website: [dilemkaya.com](https://www.dilemkaya.com)
- LinkedIn: [Dilem Kaya](https://www.linkedin.com/in/dilemkaya/)
