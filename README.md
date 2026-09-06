# Wagism

A class model of **capitalism** — the social system of wage-labour and capital — and of its interaction with the material world.

The model is built in PlantUML. It follows Karl Marx’s materialist presentation (especially *Capital* and the *Grundrisse* introduction) and the Socialist Party of Great Britain’s summaries of that presentation. Samuel A. Chambers’s treatment of capitalist categories as historically specific *objects of analysis* (not as a reified “economy”) informs the modelling style.

No application code belongs in this project. The artefacts are:

- PlantUML class diagrams under `models/`
- Model notes under `notes/`

## Method

Marx distinguishes **abstract** determinations (simple, one-sided relations that never exist on their own) from the **concrete** (a historically specific whole that is the concentration of many determinations). That distinction maps directly onto object-oriented modelling: abstract types for simple determinations; concrete types for historically specific social forms; composition for dual character.

The real subject — society in nature — remains outside the model. The diagrams are a way of appropriating that concrete in thought, not a metaphysics of self-moving concepts.

PlantUML stereotypes (`historically specific`, `transhistorical`, `abstract det.`, and the rest) are defined in [notes/stereotypes.md](notes/stereotypes.md).

## Current scope

1. Marx’s theory of (surplus) value — notes in [notes/surplus-value.md](notes/surplus-value.md), source in four files:
   - [surplus-value-overview.puml](models/surplus-value-overview.puml) — the abstract-to-concrete spine
   - [surplus-value-labour-process.puml](models/surplus-value-labour-process.puml) — I. material reproduction
   - [surplus-value-commodity.puml](models/surplus-value-commodity.puml) — II. commodity and value
   - [surplus-value-capital.puml](models/surplus-value-capital.puml) — III. wage-labour and capital

Later increments can add competition and prices of production, accumulation, the state, and world market, always rising from these abstract determinations toward a richer concrete.

![Surplus value overview](models/rendered/surplus-value-overview.svg)

## Rendering the diagrams

```bash
plantuml -tsvg -o rendered models/surplus-value-*.puml
```

Each file is a single, self-contained `@startuml`/`@enduml` diagram — deliberately one diagram per file, not one file with several `@startuml` blocks, since several GitHub PlantUML viewers (and the public plantuml.com renderer) handle multi-diagram files unreliably. Rendered SVGs are committed under `models/rendered/` and embedded in the notes and this README, so the diagrams are visible on GitHub for everyone, independent of any browser extension.
