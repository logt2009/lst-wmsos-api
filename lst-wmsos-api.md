# API Light Stock WMSOS

## Design your stock with total flexibility
- Position: Any container of stock or can change of zone. (For example un pallet)
    - You can define a position with a unique Id in all system. This is usefull for the container code.
- Zone: Area where the positions are located.

## Example: Simple stock in a store.

### Zones and positions:
- Zone type Z: Identify a zone in the store.
- Position Type H: For hang garment.
- Position Type F: For flat garment.

| Type | Id | Description | Parent | |
|------|----|-------------|--------|-|
| Z | Z01 | Front Left Store | R ||
| Z | Z02 | Front Center Store | R ||
| Z | Z03 | Front Right Store | R ||
| Z | Z11 | Back Left Store | R ||
| Z | Z12 | Back Center Store | R ||
| Z | Z13 | Back Right Store | R ||
| Z | Z99 | Back room | R ||
| H | H1001 | Rack | RZ01 | * Add positions you want in all zones |
| F | F1001 | Shelf | RZ01 | * Add positions you want in all zones |

### Stock Positions

| POSITION | SKU | STATE | AMOUNT |
|----------|-----|-------|--------|
| RZ01H1001 | 341112201 | AVAILABLE | 20 |
| RZ01H1001 | 341112202 | AVAILABLE | 22 |
| RZ99H1001 | 341112201 | AVAILABLE | 10 |
| RZ99H1001 | 341112201 | BOOKED | 1 |

Do you want know if for a SKU have garments in the back room?
Can you booked/block cothes for a client?
Can you know if you need refull a shelf?
Can you know the total amount for a SKU?

## Example: Complex distribution center.
- Zone type Z: Identify a installation in a warehouse.
- Zone type A: Identify a area into installation.
- Zone type W: Corridor
- Position type P: Position of stock in a installation.
- Position Type C: Container of garments.
- Position type PL: Pallet

| Type | Id | Description | Parent |* HG = Hang Garment |
|------|----|-------------|--------|-|
| Z | Z101 | Inbound | R ||
| Z | Z201 | Flat Sequence Buffer ||
| Z | Z211 | HG in Buffer ||
| Z | Z301 | Manual Stock | R ||
| Z | Z311 | Silo 1 | R ||
| Z | Z312 | Silo 2 | R ||
| Z | Z401 | Flat Sort 1 | R ||
| Z | Z402 | Flat Sort 2 | R ||
| Z | Z411 | HG Sort 1 | R ||
| Z | Z501 | Shipping | R ||
| A | A01 | Area 1 | RZ301 ||
| A | A01 | Area 2 | RZ301 ||
| W | W01 | Corridor 1 | RZ301A01||
| P | P001 | Position 1| RZ301A01W01 | ** Position 1 in distinct installations|
| P | P002 | Position 2 | RZ301A01W01 ||
| P | W01 | Corridor 1 | RZ311 ||
| P | W02 | Corridor 2 | RZ311 ||
| P | P001 | Position 1 | RZ311W01 |*|
| P | P001 | Position 1 | RZ311W02 |* Position 1 in distinct corridors |
| C | C10000 | Container 10000 | RZ311W02P001 ||


