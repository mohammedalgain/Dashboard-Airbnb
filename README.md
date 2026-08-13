# Airbnb Pricing Dashboard (Tableau)

An interactive Tableau dashboard analyzing an Airbnb listings dataset — pricing by
neighborhood, geography, bedroom count, and time, built on a federated join between a
listings table and a nightly calendar table.

![Dashboard preview](assets/dashboard-preview.png)

## What it shows

The main dashboard combines three views: average price per bedroom count, a geographic
choropleth of price by zip code, and price by zip code as a bar chart. Beyond the main
dashboard, the workbook includes five supporting sheets:

![Sheet overview](assets/sheets-overview.png)

## Data

The workbook joins two tables on `listing_id`:
- **Listings** — one row per property (price, room type, bedrooms, location, host and
  review fields)
- **Calendar** — nightly price and availability per listing, which is what drives the
  dataset's size (listings × days)

**The underlying dataset isn't included in this repo** — at that size, it doesn't belong
in git, and it's sourced from a local Excel export rather than something redistributable.
The workbook's data connection will need to be repointed at your own copy of the same
listings + calendar tables (Tableau will prompt for this — see below).

## Opening the dashboard

1. Install [Tableau Desktop](https://www.tableau.com/products/desktop) or the free
   [Tableau Public](https://public.tableau.com/) app.
2. Open `Airbnb_Pricing_Dashboard.twb`.
3. Tableau will prompt that it can't find the original data source — point it at your
   own Listings + Calendar Excel file with matching column names.

## Note on the screenshots

These previews are pulled from Tableau's own embedded thumbnail cache in the `.twb`
file rather than a fresh export, so they're small and a little soft — accurate to the
dashboard, just not high-resolution. If you have Tableau installed, exporting proper
full-size images (Dashboard → Export Image) and swapping them into `assets/` would be
a nice upgrade for the repo.

## Tech stack

- **Tableau** — dashboard authoring, joins, and geographic visualization
