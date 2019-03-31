# How Griddly Works as a Business Entity

## Profit Sharing

Griddly is a commercial service, though one with a substantial commitment to research and non-profit access. It sells data which has been collected and verified by a community of contributors, and it is a core aspect of the service that those contributors share in the proceeds.

The revenue coming into Griddly is allocated between various categories, according to the basic value chain that stretches from the basic operations of the platform, to data collection, to the delivery of the data to customers.

| Value       | Share | Recipient    | Description
| ----------- | ----- | -----------  | -----------
| Delivery    | 15†   | Griddly Org  | Direct costs of providing the service (cloud bills and some dev ops, mostly)
| Platform    | 40    | Griddly Org  | Platform operations, including management, finance, R&D, maintenance
| Observation | 40    | Contributors | The observation and entry of new data, as well as the periodic re-checking of an observation to confirm validity or provide updates
| Recruiting  | 5     | Anyone      | Accrues to the person who brought the collector to the platform; otherwise goes to the platform

† Delivery costs to be adjusted from time to time

Note that these distributions are calculated on a per-datapoint basis and summed across all data delivered within each customer transaction.

## Observation Aging and Refresh

10 slots, each corresponding to six months (so 5 years total)
On initial observation, all slots go to observer
On validation, slots 2 and 4 go to validator (can be observer if self-certifying)
On correction, it is as if the observation was newly-made: all slots are given to the corrector, and validation is re-opened
Every six months, slots shift left and slot 1 is removed; slot 10 is filled by the first to re-confirm, and remains with the observer until that refresh observation has occurred

## Reputation

* Achievements / Badges
* Number of observations
* Number of corrections (all time, last year, last month)

In this way, Griddly incentivizes both the *accurate* collection of new data *and* the re-confirmation of existing observations
