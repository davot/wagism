# Modelling stereotypes

PlantUML stereotypes on this project are not software-engineering jargon. They mark *what kind of determination* a type is in a materialist class model of capitalism.

They answer three different questions:

- **When does this exist?** — in any human society, or only under a definite social form?
- **How one-sided is it?** — a simple determination that never appears alone, or a richer historical form?
- **What kind of thing is it?** — a material bearer, a social relation, or a personification of a class role?

A type may carry more than one stereotype (`Capital` is both historically specific and a social relation).

---

## `historically specific`

A type that exists only under a definite social form — here, commodity production or capitalism — and not as a feature of human life as such.

It is the opposite of `transhistorical`. Humans always work on nature and produce use-values. They do not always produce *commodities*, sell *labour-power*, or confront their own products as *capital*. Those belong to a particular epoch, with particular class relations.

The stereotype is a materialist warning: do not treat the type as natural, eternal, or as “how production works in general.”

`LabourPower` is transhistorical: the capacity to work is embodied in living individuals whenever people work. `LabourPowerAsCommodity` is historically specific: that capacity is *sold* only when producers are separated from the means of production and must work for a wage. The same person, the same muscles and brain — a different social form.

`Capital` is the same kind of mark. A machine is a means of production in any society that uses machines. It is *capital* only when it is used to command wage-labour for surplus value. Drop that class relation and the stereotype says the type no longer applies.

Two finer points:

- **Not “recent” or “dated.”** Feudal rent was historically specific too. The label means *bound to a social form*, not *modern*.
- **Not the same as UML “concrete class.”** A historically specific type can still be a simple determination relative to a richer whole (`Commodity` is more concrete than `Value`, less concrete than `Capital`). The stereotype answers *when and under what social relations this exists*, not *whether the class can be instantiated in software*.

That is also the modelling stance taken from Samuel A. Chambers: these are objects of a capitalist (or commodity) social order, not natural kinds, and there is no reified `Economy` standing outside those relations.

---

## The other stereotypes

| Stereotype | What it flags |
| --- | --- |
| `transhistorical` | Material conditions of any human society (nature, labour process, use-value, labour-power as a *capacity*) |
| `abstract det.` | A simple, one-sided determination that never appears on its own (`Value`, `AbstractLabour`) |
| `historically specific` | A social form that only exists in a given historical order (`Commodity`, `Capital`, `Wage`, `SurplusValue`) |
| `social relation` | Not a physical property of a thing. Value is not in the diamond; capital is not the machine. |
| `personification` | An individual as bearer of a class relation (`WageLabourer`, `Capitalist`), not a moral type or a theory of human nature |

`transhistorical` and `historically specific` are one cut (any society vs a definite social form). `abstract det.` is a different cut (simple determination vs richer concrete). Do not collapse them.

`abstract det.` types are usually also UML-abstract: they cannot “exist alone.” Value never appears as such; it appears as exchange-value, as money, as capital. The labour process never exists in general, only as slave, peasant, artisan, wage, and so on.

---

## How this relates to abstract and concrete

Marx’s method of rising from the abstract to the concrete (Grundrisse) is the other axis of the model. It is documented in [surplus-value.md](surplus-value.md) §2.

A historically specific type is often *more concrete* than the transhistorical or abstract determination it specialises (`LabourProcess` → `CapitalistProductionProcess`; `LabourPower` → `LabourPowerAsCommodity`; `Value` → `Capital`). “More concrete” here means *more determinations concentrated*, not “more real.” The real subject — society in nature — was always already concrete.
