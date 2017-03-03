# Scraping Guide

The goal of this guide is to help decide when a web scraper is necessary, and then to show how to build a scraper.

### Picking a dataset

Starting with [datasets that have been published](https://github.com/daniellecrobinson/Data-Rescue-PDX/tree/master/datarefuge-json) to DataRefuge.org, find one suitable for writing a scraper (you may need to try a couple)

### Finding the datasets "bag" zip and other existing metadata

Using [this metadata](https://www.datarefuge.org/api/3/action/package_search?rows=1000), find your UUID that you adopted. Download the "bag" .zip and see what data the original harvester was able to gather

You can also check https://www.archivers.space/ for your UUID (the workflow tool the harvester originally used) and check for other comments/links to maybe an existing scraper if one exists

### Claim your dataset

If you find one, register it in [this spreadsheet](https://docs.google.com/spreadsheets/d/1Ojgw9-VFdwO2Qxrp9a6W6X8FFS4047uhvCf8Lw3Q6gU/edit#gid=1105874853) and put in notes that you're working on a scraper

When you decide a scraper is necessary, use these examples to work from:

Hoyt Arboretum Python Notebook: https://github.com/stevenbedrick/march_datajamboree
National Parks Scraper: https://github.com/ekansa/data-rescue-nps-irma

### What should your scraper do?

- Design it to run on some interval (daily, weekly, however often the data changes)
- It should crawl the web page and identify HTTP/FTP links to downloadable raw data
- It should produce a list of links every time it runs. This list can be fed into a downloading/harvesting program
