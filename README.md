# tufe-rates

Public data source for the Kira Artışı app: TÜİK's "CPI twelve-month averages change rate" series (the legal ceiling for rent increases in Turkey, TBK m.344).

## Consumption

```
https://raw.githubusercontent.com/sameterkanboz/tufe-rates/main/tufe-rates.json
```

## Key semantics

`rates` keys are **TÜİK data months** (`YYYY-MM`), not the months the increase applies to. A contract renewed in month M uses the rate of month M-1. Most rent tables on the web label rates by renewal month — shift back one month when importing from them.

## Update process

1. TÜİK publishes the CPI bulletin around the 3rd of each month at 10:00: https://data.tuik.gov.tr
2. Add the "twelve-month averages change" value under the data-month key
3. Bump `updatedAt` (clients pick the table with the newer `updatedAt`)
