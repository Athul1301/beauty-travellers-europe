# Data files

Two small tables I collected by hand. Every other dataset in this project (tourism nights, airport passengers, exchange rates) is read straight from Eurostat by Power BI, so it is not stored here.

## prices.csv

Shelf prices for 24 beauty products (8 fragrance, 11 makeup, 5 skincare), collected on 19 November 2026.

| Column | Meaning |
|---|---|
| product_id | F = fragrance, M = makeup, S = skincare |
| brand, product, category | What the product is |
| size_ml | Size, when the product is sold by volume |
| location | Country, or "Paris CDG" for the airport |
| channel | Downtown (European shop), Duty free (CDG), Home market (where the traveller lives) |
| currency, price | Price as shown on the page, in local currency |
| price_note | Where the price comes from and anything to know about it |
| collected_on | Date the price was read |
| source_url | Link to the page |

Rules I used:

- **Normal shelf price.** If a shop was running a sale, I kept the normal price and wrote the sale price in the note.
- **Duty free = Paris CDG only** (Extime online shop). I kept the standard price, not the 10% member price.
- **Brand's own website first.** Where the brand has no shop in a country, I used the main authorised retailer and labelled it "Retailer price": Sephora France, Sephora US, Sephora Brasil, Nykaa in India, Dior's official China site.
- **Tax.** US prices are before sales tax. Every other price includes VAT or local tax.
- **Gaps.** An empty price means I could not find the product at that place. The note says why.

## policy_tracker.csv

12 government decisions and travel trends that can push travellers' shopping in Europe up or down.

| Column | Meaning |
|---|---|
| id | P01 to P12 |
| date | When it starts or was announced (2026-Q4 when only the quarter is known) |
| applies_to, applies_type | Which country or traveller group it concerns |
| measure | What happened, in one line |
| effect | Boost, Slow or Watch |
| confidence | How solid the sources are |
| source_1, source_2 | An official source, or two reliable news outlets |

## Not included

Exchange rates are not stored here. Power BI reads the monthly euro rates from Eurostat (`ert_bil_eur_m`). The dirham and riyal are fixed to the US dollar, so those two are converted through it.
