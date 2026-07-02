# SAP Procure to Pay Transaction Guide

This guide explains the SAP transaction codes and the three way match logic used in the simulation. It is written plainly so it also works as interview preparation.

## The procure to pay cycle

Procure to pay is the full journey from deciding to buy something to paying the supplier for it. In SAP, three transaction codes carry the core of that journey.

### ME21N — Create Purchase Order

The buyer raises a purchase order (PO) against an approved supplier. The PO records what is being bought, how much, at what price, and when it is expected. This is the commitment: the business is now on the hook to receive and pay for these goods.

In the data, every PO begins with an ME21N line. System status: **PO Created**.

### MIGO — Post Goods Receipt

When the goods physically arrive at the warehouse, the receipt is posted against the PO. This is where reality meets the order. If 100 units were ordered and only 80 arrive, MIGO is where that shortage first shows up.

In the data, MIGO lines carry the received quantity. A short delivery shows a **GR SHORT** status.

### MIRO — Verify and Post Invoice

The supplier sends an invoice. Before it is paid, it is checked against the PO and the goods receipt. This is the moment the business decides whether to release money.

In the data, MIRO lines carry the invoice amount. The outcome is either **CLEARED** or **BLOCKED**.

## The three way match

The three way match is the control that protects the business from paying for the wrong thing. It compares three documents:

1. **The Purchase Order** — what we agreed to buy and at what price
2. **The Goods Receipt** — what actually arrived
3. **The Invoice** — what the supplier is charging

If all three agree, the invoice clears for payment. If any disagree, it is blocked and held for review.

| Check | Question it answers | What blocks it |
|---|---|---|
| Quantity match | Did we receive what we are being billed for? | Goods receipt is short of the order |
| Price match | Are we being charged the agreed price? | Invoice price exceeds the PO price |

## How the exceptions play out in the data

The simulation engineers three outcomes so the logic has something to catch.

- **Clean loop (5 POs).** Order, receipt, and invoice all agree. Invoice clears. This is what good looks like.
- **Freight shortage (3 POs).** Fewer goods arrived than ordered. Quantity match fails. Invoice blocked until resolved.
- **Price variance (3 POs).** The supplier billed above the agreed price. Price match fails. Invoice blocked, protecting the business from overpaying.

The result: 6 of 11 invoices were correctly held, protecting $19,256 from premature payment and catching $1,021 in overcharges before money left the business.

## Why this matters to an employer

A purchasing officer who understands the three way match understands where a business quietly loses money: paying for goods that never arrived, and paying prices nobody agreed to. The whole point of the control is that trust is not a substitute for checking.
