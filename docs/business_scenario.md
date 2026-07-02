# Business Scenario: AusTrade Wholesale Distribution

## The company

AusTrade Wholesale Distribution is a fictional Melbourne based wholesaler supplying electrical, industrial, and safety equipment to construction and manufacturing customers across Victoria. It is modelled on the kind of mid sized wholesale distributor common across Melbourne's west and south east.

The business runs a single distribution centre (plant AU01) and manages 20 active materials across five key suppliers. It imports from China, Vietnam, and Germany, and sources locally from Australian vendors.

## The role being simulated

The project is built from the perspective of a **procurement analyst** on the purchasing team. The daily responsibilities modelled here are the real responsibilities of a purchasing officer or procurement assistant:

- Raising purchase orders against approved suppliers
- Confirming goods received match what was ordered
- Verifying supplier invoices before they are paid
- Monitoring supplier contracts and acting on renewals
- Reporting spend and exceptions to management

## Why these five suppliers

The vendor mix is deliberate, so the data reflects real sourcing decisions.

| Vendor | Country | Why they are in the mix |
|---|---|---|
| Guangzhou ElecTech | China | Lowest unit cost, largest spend, single source risk |
| Hanoi Industrial Supplies | Vietnam | Secondary low cost source, contract expiring |
| Mueller GmbH Electrical | Germany | Premium quality, priced below current market |
| Brisbane Safety Supplies | Australia | Local, fast lead time, safety lines |
| Sydney Solar Components | Australia | Local, higher value solar components |

## The tension in the data

Good procurement data tells a story. This dataset was built around four real tensions a purchasing team manages:

1. **Cost versus risk.** The cheapest supplier (Guangzhou) carries 44 percent of spend. That is efficient on price and dangerous on dependency.
2. **Trust versus control.** Suppliers do not always deliver what was ordered or invoice what was agreed. The three way match exists because trust is not a control.
3. **Price creep.** Contracted prices drift from market prices over time. The contract tracker exists to catch that drift before it costs money.
4. **Time pressure.** Contracts expire. Deliveries run late. Someone has to see it coming.

## How to talk about this in an interview

The honest framing: this is a simulation built to demonstrate command of the procure to pay process. The scenarios are engineered so the compliance logic has real exceptions to catch. When asked about it, the strongest answer connects it to real experience:

> "I built this on the procurement principles I saw at Répertoire Culinaire, where I worked with SAP purchase orders, customs, and stock receipting, applied to a wholesale distribution scenario. I wanted to understand the full purchase to pay cycle end to end and the controls that protect a business from overpaying."
