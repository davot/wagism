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

1. [Marx’s theory of (surplus) value](models/surplus-value.puml) — notes in [notes/surplus-value.md](notes/surplus-value.md)

Later increments can add competition and prices of production, accumulation, the state, and world market, always rising from these abstract determinations toward a richer concrete.

## Rendering the diagrams

```bash
plantuml -tsvg models/surplus-value.puml
```

The source file contains several diagrams (overview, then three levels of concretion). SVG renderings are written to `models/rendered/` when that command is run.
