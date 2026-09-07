# Relationships — model reference

A complete inventory of every relationship drawn in the diagrams, organised by diagram, plus the notation used to draw them. Companion to [stereotypes.md](stereotypes.md) (which documents the *classes*); this file documents the *lines between them*.

This is a reference, not a replacement for the notes. Read [surplus-value.md](surplus-value.md), [accumulation.md](accumulation.md), and [finance.md](finance.md) for why each relationship holds; use this file to look one up quickly, or to check the model for consistency.

---

## Notation

PlantUML's arrow syntax is used deliberately, not decoratively. The choice of notation for a given line encodes a claim about the *kind* of connection between two determinations — the same distinction of kind that the abstract/concrete method draws (see [surplus-value.md §2](surplus-value.md#2-abstract-and-concrete--why-this-is-an-object-model)).

| Notation | UML name | Used in this model for |
| --- | --- | --- |
| `A --> B` | Directed association | A real, directed relation: A acts on, produces, sells to, or is otherwise related to B. Neither side's identity depends on the other. |
| `A ..> B` | Dependency | A weaker or conditional link: A gives rise to, presupposes, or (with a negating label) rules out B. Used where the connection is real but looser than a standing association — often where one side is a historical becoming or a hypothetical limiting case. |
| `A *-- B` | Composition | B is an inseparable part of A; A's own definition includes B. The chief use is **dual character**: a single real thing or process (`Commodity`, `Capital`) composed of two social aspects that cannot exist apart from the whole. |
| `A o-- B` | Aggregation | B is a constituent *moment* of process A — gathered into it to make it up, but a slightly looser relation than composition (used for the labour process's moments: object, instrument, living labour). |
| `A --\|> B` | Generalization (inheritance) | A is a more concrete, more historically specific form of B — "A is a kind of B." Used for the rising concretion the whole model is built on (`MeansOfSubsistence --\|> UseValue`, `LabourPowerAsCommodity --\|> LabourPower`). |
| `A ..\|> B` | Realization | A is the *same* real activity or thing, counted under aspect B. Used only for `LivingLabour`, which realizes both `ConcreteLabour` and `AbstractLabour` — the two social aspects are not proper superclasses (labour cannot simply "be a kind of" an abstraction it makes real), so the weaker, dashed realization arrow is used rather than solid generalization. |

Composition and generalization are almost all left **unlabelled** in the diagrams: the notation itself carries the claim ("this is dual character," "this is a more concrete form of that"), and a label would only restate it. Associations and dependencies are almost always labelled, since the notation alone doesn't say *how* A relates to B.

---

## I. Overview ([surplus-value-overview.puml](../models/surplus-value-overview.puml))

| A | | B | Label |
| --- | --- | --- | --- |
| `Nature` | `-->` | `LabourProcess` | materials |
| `LabourPower` | `-->` | `LabourProcess` | expended in |
| `LabourProcess` | `-->` | `UseValue` | produces |
| `UseValue` | `..>` | `Commodity` | produced for exchange |
| `AbstractLabour` | `-->` | `Value` | is the substance of |
| `Commodity` | `*--` | `UseValue` | *(dual character)* |
| `Commodity` | `*--` | `Value` | *(dual character)* |
| `LabourPower` | `..>` | `LabourPowerAsCommodity` | sold |
| `LabourProcess` | `..>` | `CapitalistProductionProcess` | + command + valorization |
| `Value` | `..>` | `Capital` | + self-expansion |
| `WageLabourer` | `-->` | `LabourPowerAsCommodity` | must sell |
| `Capitalist` | `-->` | `LabourPowerAsCommodity` | buys |
| `Capitalist` | `-->` | `Capital` | personifies |
| `CapitalistProductionProcess` | `-->` | `SurplusValue` | produces |
| `Capital` | `*--` | `SurplusValue` | *(dual character: capital's self-expansion realized)* |

The three unlabelled `..>` lines (`LabourProcess`→`CapitalistProductionProcess`, `Value`→`Capital`, and to a lesser extent `UseValue`→`Commodity`) are the diagram's abstract-to-concrete spine: each is a transhistorial or abstract determination becoming a richer, historically specific one, not a standing relation between two independently-existing things. That's why dependency, not association, is used for all three.

---

## II. Labour process ([surplus-value-labour-process.puml](../models/surplus-value-labour-process.puml))

| A | | B | Label |
| --- | --- | --- | --- |
| `Human` | `*--` | `LabourPower` | capacity of |
| `LabourPower` | `-->` | `LivingLabour` | expended as |
| `Human` | `-->` | `LabourProcess` | conducts |
| `LabourProcess` | `o--` | `LivingLabour` | *(moment of the process)* |
| `LabourProcess` | `o--` | `ObjectOfLabour` | *(moment of the process)* |
| `LabourProcess` | `o--` | `InstrumentOfLabour` | *(moment of the process)* |
| `ObjectOfLabour` | `--\|>` | `MeansOfProduction` | *(is a kind of)* |
| `InstrumentOfLabour` | `--\|>` | `MeansOfProduction` | *(is a kind of)* |
| `Nature` | `-->` | `ObjectOfLabour` | earth, materials |
| `LabourProcess` | `-->` | `UseValue` | produces |
| `MeansOfSubsistence` | `--\|>` | `UseValue` | *(is a kind of)* |
| `MeansOfProduction` | `--\|>` | `UseValue` | *(is a kind of)* |
| `MeansOfSubsistence` | `..>` | `LabourPower` | reproduces |
| `UseValue` | `-->` | `ObjectifiedLabour` | past labour in useful form |
| `ObjectifiedLabour` | `..>` | `InstrumentOfLabour` | tools are past labour |
| `LivingLabour` | `-->` | `MeansOfProduction` | sets in motion |

`Human *-- LabourPower` is the one composition here that isn't dual character in the value-form sense: it marks that labour-power has no existence apart from the living individual who bears it (*Capital* I, ch. 6). The three `o--` aggregations record that the labour process is *made up of* object, instrument, and living labour as its moments (Marx, *Capital* I, ch. 7) — looser than composition because these moments also have their own further relations (e.g. object and instrument are each, in turn, generalized to `MeansOfProduction`) rather than existing only as parts of this one whole.

---

## III. Commodity and value ([surplus-value-commodity.puml](../models/surplus-value-commodity.puml))

| A | | B | Label |
| --- | --- | --- | --- |
| `LivingLabour` | `..\|>` | `ConcreteLabour` | *(realizes aspect)* |
| `LivingLabour` | `..\|>` | `AbstractLabour` | *(realizes aspect)* |
| `ConcreteLabour` | `-->` | `UseValue` | produces |
| `AbstractLabour` | `-->` | `Value` | is the substance of |
| `Commodity` | `*--` | `UseValue` | bearer |
| `Commodity` | `*--` | `Value` | social form |
| `Value` | `-->` | `ExchangeValue` | appears as |
| `Value` | `-->` | `SociallyNecessaryLabourTime` | magnitude |
| `Money` | `--\|>` | `Commodity` | one commodity as general equivalent |
| `Money` | `-->` | `Value` | necessary form of appearance |
| `SimpleCommodityProduction` | `-->` | `Commodity` | produces and sells |

This diagram carries the model's central dual-character claim: `LivingLabour` is one activity realized under two aspects (`..|>`, not `--|>` — see notation table above), and that duality is what `Commodity *-- UseValue`/`*-- Value` then registers at the level of the product. `Money --|> Commodity` is a genuine generalization, unusually labelled here because "one commodity as general equivalent" states *why* money specializes commodity, which the bare arrow wouldn't convey (money is not simply *a* commodity among others; it is the commodity historically excluded to play this role).

---

## IV. Wage-labour and capital ([surplus-value-capital.puml](../models/surplus-value-capital.puml))

| A | | B | Label |
| --- | --- | --- | --- |
| `CapitalistModeOfProduction` | `*--` | `WorkingClass` | *(constitutes)* |
| `CapitalistModeOfProduction` | `*--` | `CapitalistClass` | *(constitutes)* |
| `WorkingClass` | `o--` | `WageLabourer` | *(members)* |
| `CapitalistClass` | `o--` | `Capitalist` | *(members)* |
| `WageLabourer` | `-->` | `LabourPowerAsCommodity` | sells |
| `Capitalist` | `-->` | `LabourPowerAsCommodity` | buys |
| `Capitalist` | `-->` | `MeansOfProduction` | monopolizes |
| `WageLabourer` | `..>` | `MeansOfProduction` | excluded from |
| `LabourPowerAsCommodity` | `--\|>` | `LabourPower` | *(is a kind of)* |
| `LabourPowerAsCommodity` | `--\|>` | `Commodity` | *(is a kind of)* |
| `LabourPowerAsCommodity` | `-->` | `Wage` | sold at |
| `LabourPowerAsCommodity` | `-->` | `MeansOfSubsistence` | value determined by |
| `WageLabourer` | `-->` | `MeansOfSubsistence` | consumes |
| `Capital` | `--\|>` | `Value` | *(is a kind of)* |
| `Capital` | `*--` | `ConstantCapital` | *(dual character of capital's value)* |
| `Capital` | `*--` | `VariableCapital` | *(dual character of capital's value)* |
| `ConstantCapital` | `..>` | `MeansOfProduction` | MP become capital only in this relation |
| `VariableCapital` | `..>` | `LabourPowerAsCommodity` | v laid out as wages |
| `Capitalist` | `-->` | `Capital` | advances |
| `CapitalistProductionProcess` | `--\|>` | `LabourProcess` | *(is a kind of)* |
| `CapitalistProductionProcess` | `*--` | `ValorizationProcess` | dual character |
| `CapitalistProductionProcess` | `o--` | `LivingLabour` | *(moment of the process)* |
| `CapitalistProductionProcess` | `o--` | `MeansOfProduction` | *(moment of the process)* |
| `LabourPowerAsCommodity` | `-->` | `LivingLabour` | consumed as |
| `LivingLabour` | `-->` | `ConstantCapital` | transfers c |
| `LivingLabour` | `-->` | `VariableCapital` | replaces v |
| `LivingLabour` | `-->` | `SurplusValue` | creates s |
| `ValorizationProcess` | `-->` | `WorkingDay` | *(unlabelled)* |
| `WorkingDay` | `-->` | `SurplusValue` | surplus labour-time |
| `Capital` | `*--` | `SurplusValue` | appropriates s |

This is the largest diagram and it is where every generalization arrow does real theoretical work: `LabourPowerAsCommodity --|> LabourPower` and `--|> Commodity` together say that labour-power-as-commodity is *both* a specialisation of the transhistorical capacity to work *and* a specialisation of the historically specific commodity-form — it inherits from both determinations, which is exactly why its sale is the hinge of the whole model (surplus-value.md §7). `Capital *-- ConstantCapital`/`*-- VariableCapital` is a second, independent dual-character split from `Capital *-- SurplusValue`: the first divides capital's *value* by role in producing new value; the second identifies what capital *appropriates* as a result. Both are true of the same `Capital` at once, at different points in its circuit.

---

## V. Accumulation of capital ([accumulation.puml](../models/accumulation.puml))

| A | | B | Label |
| --- | --- | --- | --- |
| `Capital` | `*--` | `SurplusValue` | appropriates |
| `SurplusValue` | `-->` | `Revenue` | part consumed unproductively as |
| `SurplusValue` | `-->` | `AccumulationOfCapital` | part capitalised as |
| `SurplusValue` | `..>` | `SimpleReproduction` | if wholly consumed (never sustained) |
| `AccumulationOfCapital` | `-->` | `ConstantCapital` | expands |
| `AccumulationOfCapital` | `-->` | `VariableCapital` | expands |
| `AccumulationOfCapital` | `-->` | `Capital` | reconverted into additional capital |
| `Capitalist` | `-->` | `AccumulationOfCapital` | executes (bearer, not author) |
| `Capitalist` | `-->` | `Revenue` | draws personal consumption from |
| `CapitalistCompetition` | `-->` | `Capitalist` | compels accumulation (independent of will) |
| `CapitalistCompetition` | `..>` | `SimpleReproduction` | rules out as a lasting state |

Two things to notice in this diagram's relations specifically, since they carry the increment's whole argument (see [accumulation.md §2](accumulation.md#2-the-argument-necessity-not-choice)):

- `CapitalistCompetition --> Capitalist` is the only relation in the whole model where the *label itself* asserts a modal claim ("independent of will") rather than just naming an action. That is deliberate: this is the one line that has to carry the "not a political choice" argument, so it is spelled out rather than left to a bare verb.
- `AccumulationOfCapital --> Capital` closes a loop: `Capital *-- SurplusValue` → `SurplusValue --> AccumulationOfCapital` → `AccumulationOfCapital --> Capital`. That cycle *is* the diagram of self-expanding value (`M – C … P … C′ – M′`, already given as an attribute of `Capital` in surplus-value-capital.puml) — accumulation is what makes the circuit repeat on a larger scale rather than close once.

---

## VI. Credit and banking ([finance.puml](../models/finance.puml))

| A | | B | Label |
| --- | --- | --- | --- |
| `Capital` | `*--` | `SurplusValue` | appropriates |
| `SurplusValue` | `-->` | `IndustrialProfit` | part retained as |
| `SurplusValue` | `-->` | `Interest` | part paid as |
| `InterestBearingCapital` | `-->` | `Interest` | claims |
| `Capitalist` | `-->` | `IndustrialProfit` | receives |
| `Capitalist` | `-->` | `Interest` | pays out of s |
| `Capitalist` | `-->` | `Loan` | borrows |
| `IdleMoneyCapital` | `-->` | `Deposit` | placed as |
| `CommercialBank` | `-->` | `Deposit` | borrows (retail) |
| `CommercialBank` | `-->` | `MoneyMarket` | borrows (wholesale) |
| `CommercialBank` | `-->` | `Loan` | advances obtained funds as |
| `Banker` | `-->` | `CommercialBank` | personifies |
| `IdleMoneyCapital` | `-->` | `Loan` | activated as (not created) |
| `CommercialBank` | `-->` | `Interest` | collects the spread |
| `CentralBank` | `-->` | `FiatCurrency` | issues |
| `CentralBank` | `-->` | `BankReserves` | creates |
| `CommercialBank` | `-->` | `BankReserves` | holds / settles with |
| `Loan` | `-->` | `BankReserves` | when spent, settled by transfer of |
| `ThinAirTheory` | `..>` | `Loan` | mistakes the book entry for |
| `CommercialBank` | `..>` | `ThinAirTheory` | cannot enact |
| `BankReserves` | `..>` | `ThinAirTheory` | settlement rules out |

The load-bearing claims of this increment sit on two clusters of arrows (see [finance.md](finance.md)):

- `SurplusValue --> Interest` and `CommercialBank --> Interest : collects the spread` say that banking profit is a *share* of unpaid labour, not a second source. That is why there is no arrow from `Loan` or `CommercialBank` to `SurplusValue` labelled "produces."
- `CentralBank --> FiatCurrency` / `--> BankReserves` is the only place new currency is issued. `Loan --> BankReserves : when spent, settled by transfer of` and `BankReserves ..> ThinAirTheory` are the funding constraint: the book entry that pairs a loan with a deposit is not the central bank's fiat issue.

`ThinAirTheory` is a contrast class, like `SimpleReproduction` and `SimpleCommodityProduction`: a determination the real relation rules out, typed so the denial is visible in the diagram and not only in the notes.

---

## Cross-diagram note: classes that recur

`Capital`, `SurplusValue`, `Capitalist`, `ConstantCapital`, `VariableCapital`, `LabourProcess`, `LivingLabour`, `MeansOfProduction`, `MeansOfSubsistence`, `Commodity`, `Value`, and `LabourPower` each appear in more than one file (`Interest` and the banking types are introduced only in finance.puml) (full definition given once, in the most concrete diagram where they're introduced; recapped with a short body elsewhere — see each `.puml` file's header comment for which file holds the full definition). Their relationships *within* each diagram are independent per-file — this document does not merge them into one graph — because each diagram is deliberately a different, self-contained level of concretion (see [surplus-value.md §2](surplus-value.md#2-abstract-and-concrete--why-this-is-an-object-model)), not a fragment of one master diagram.
