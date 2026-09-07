# Wagism

A class model of **capitalism** — the social system of wage-labour and capital — and of its interaction with the material world.

The model is built in PlantUML. It follows Karl Marx’s materialist presentation (especially *Capital* and the *Grundrisse* introduction) and the Socialist Party of Great Britain’s summaries of that presentation. Samuel A. Chambers’s treatment of capitalist categories as historically specific *objects of analysis* (not as a reified “economy”) informs the modelling style.

No application code belongs in this project. The artefacts are:

- PlantUML class diagrams under `models/`
- Model notes under `notes/`

## Method

Marx distinguishes **abstract** determinations (simple, one-sided relations that never exist on their own) from the **concrete** (a historically specific whole that is the concentration of many determinations). That distinction maps directly onto object-oriented modelling: abstract types for simple determinations; concrete types for historically specific social forms; composition for dual character.

The real subject — society in nature — remains outside the model. The diagrams are a way of appropriating that concrete in thought, not a metaphysics of self-moving concepts.

PlantUML stereotypes (`historically specific`, `transhistorical`, `abstract det.`, and the rest) are defined in [notes/stereotypes.md](notes/stereotypes.md). Every relationship in every diagram — what it connects, what notation it uses, and why — is indexed in [notes/relationships.md](notes/relationships.md).

## Current scope

1. Marx’s theory of (surplus) value — notes in [notes/surplus-value.md](notes/surplus-value.md), source in four files:
   - [surplus-value-overview.puml](models/surplus-value-overview.puml) — the abstract-to-concrete spine
   - [surplus-value-labour-process.puml](models/surplus-value-labour-process.puml) — I. material reproduction
   - [surplus-value-commodity.puml](models/surplus-value-commodity.puml) — II. commodity and value
   - [surplus-value-capital.puml](models/surplus-value-capital.puml) — III. wage-labour and capital
2. Accumulation of capital — why accumulation is a compulsion of competition among many capitals, not a policy choice — notes in [notes/accumulation.md](notes/accumulation.md), source in [accumulation.puml](models/accumulation.puml)
3. Credit and banking — interest as a share of surplus value; commercial banks intermediate, only the central bank issues fiat — notes in [notes/finance.md](notes/finance.md), source in [finance.puml](models/finance.puml)
4. Fictitious capital — shares and government bonds as capitalised claims on future surplus value, not a second real capital — notes in [notes/fictitious-capital.md](notes/fictitious-capital.md), source in [fictitious-capital.puml](models/fictitious-capital.puml)
5. Prices of production — competition levels the rate of profit and redistributes surplus value; it does not create it — notes in [notes/prices-of-production.md](notes/prices-of-production.md), source in [prices-of-production.puml](models/prices-of-production.puml)
6. Concentration, centralisation, and the reserve army — the general law of capitalist accumulation — notes in [notes/concentration.md](notes/concentration.md), source in [concentration.puml](models/concentration.puml)
7. The capitalist state — public power of the class, tax as a share of the product, nationalisation as still capital — notes in [notes/state.md](notes/state.md), source in [state.puml](models/state.puml)

Later increments can add reproduction schemas, the falling rate of profit, crises, ground rent, and world market, always rising from these abstract determinations toward a richer concrete.

![Surplus value overview](models/rendered/surplus-value-overview.svg)

## Rendering the diagrams

```bash
plantuml -tsvg -o rendered models/*.puml

# PlantUML's SVG output has a transparent background (`skinparam
# backgroundColor white` is a no-op for SVG on at least plantuml
# 1.2020.02). A transparent background renders as black-on-black —
# relationship labels become unreadable — in dark-mode browsers/viewers.
# Force an opaque white background by inserting a full-canvas rect as
# the first drawn element of each SVG:
for f in models/rendered/*.svg; do
  sed -i '0,/<defs\/><g>/{s//<defs\/><rect width="100%" height="100%" fill="#FFFFFF"\/><g>/}' "$f"
done
```

Each file is a single, self-contained `@startuml`/`@enduml` diagram — deliberately one diagram per file, not one file with several `@startuml` blocks, since several GitHub PlantUML viewers (and the public plantuml.com renderer) handle multi-diagram files unreliably. Rendered SVGs are committed under `models/rendered/` and embedded in the notes and this README, so the diagrams are visible on GitHub for everyone, independent of any browser extension.
