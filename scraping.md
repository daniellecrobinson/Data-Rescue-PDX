# Scraping Guide

The goal of this guide is to help decide when a web scraper is necessary, and then to show how to build a scraper.

As part of DataRefuge.org, many datasets have been nominated for backup, and an initial backup has been made. However many of these are one time captures. Sometimes a scraper would be useful to monitor/discover new changes to data in the future automatically.

### 1. Picking a dataset

Starting with [datasets that have been published](https://github.com/daniellecrobinson/Data-Rescue-PDX/tree/master/datarefuge-json) to DataRefuge.org, find one suitable for writing a scraper (you may need to try a couple)

### 2. Finding the datasets "bag" zip and other existing metadata

Using [this metadata](https://www.datarefuge.org/api/3/action/package_search?rows=1000), find your UUID that you adopted. Download the "bag" .zip and see what data the original harvester was able to gather

You can also check https://www.archivers.space/urls?phase=done for your UUID (the workflow tool the harvester originally used) and check for other comments/links to maybe an existing scraper if one exists

### 3. Claim your dataset

If you find one, register it in [this spreadsheet](https://docs.google.com/spreadsheets/d/1Ojgw9-VFdwO2Qxrp9a6W6X8FFS4047uhvCf8Lw3Q6gU/edit#gid=1105874853) and put in notes that you're working on a scraper

When you decide a scraper is necessary, use these examples to work from:

Hoyt Arboretum Python Notebook: https://github.com/stevenbedrick/march_datajamboree
National Parks Scraper: https://github.com/ekansa/data-rescue-nps-irma

### 4. What should your scraper do?

- Design it to run on some interval (daily, weekly, however often the data changes)
- It should crawl the web page and identify HTTP/FTP links to downloadable raw data
- It should produce a list of links every time it runs. This list can be fed into a downloading/harvesting program

### Example

This is an example using the steps above

#### Step 1

Lets use the [first dataset from the datarefuge-json folder](https://github.com/daniellecrobinson/Data-Rescue-PDX/blob/master/datarefuge-json/0c7a3f3a-4e9c-4c16-8964-cac95a5a6a55.json) as an example

#### Step 2

By searching for our UUID 0c7a3f3a-4e9c-4c16-8964-cac95a5a6a55 on [https://www.datarefuge.org/api/3/action/package_search?rows=1000](this) we found our metadata from data.refuge.org is:

```json
{
  "license_title": "Other (Public Domain)",
  "maintainer": "",
  "relationships_as_object": [],
  "private": false,
  "maintainer_email": "",
  "num_tags": 3,
  "id": "ed03a990-7131-410e-ad60-108cc53a5a6e",
  "metadata_created": "2017-02-18T00:43:56.597170",
  "metadata_modified": "2017-02-20T16:37:18.657113",
  "author": "",
  "author_email": "",
  "state": "active",
  "version": "",
  "creator_user_id": "cfbd37b2-ddc2-40fc-8609-b7ae4eec8f45",
  "type": "dataset",
  "resources": [
    {
      "mimetype": null,
            "cache_url": null,
            "hash": "",
            "description": "",
            "name": "0c7a3f3a-4e9c-4c16-8964-cac95a5a6a55_Bag.zip",
            "format": "ZIP",
            "url": "https://www.datarefuge.org/dataset/ed03a990-7131-410e-ad60-108cc53a5a6e/resource/b9846492-1aab-4b6d-ab88-c470e7b08671/download/0c7a3f3a-4e9c-4c16-8964-cac95a5a6a55_bag.zip",
            "cache_last_updated": null,
            "package_id": "ed03a990-7131-410e-ad60-108cc53a5a6e",
            "created": "2017-02-18T00:44:41.794936",
            "state": "active",
            "mimetype_inner": null,
            "last_modified": null,
            "position": 0,
            "revision_id": "341a53d4-a3cf-47eb-8313-b59cb979216e",
            "url_type": "upload",
            "id": "b9846492-1aab-4b6d-ab88-c470e7b08671",
            "resource_type": null,
            "size": null
          }
        ],
        "num_resources": 1,
        "tags": [
          {
            "vocabulary_id": null,
            "state": "active",
            "display_name": "fire",
            "id": "ea630aae-e749-48cf-a86d-7865eddb09a5",
            "name": "fire"
          },
          {
            "vocabulary_id": null,
            "state": "active",
            "display_name": "fire detection",
            "id": "9f3deeb2-d057-49f1-ae56-b708f5814e8a",
            "name": "fire detection"
          },
          {
            "vocabulary_id": null,
            "state": "active",
            "display_name": "mapping",
            "id": "32878964-a441-4796-965c-0ecdc5a63a58",
            "name": "mapping"
          }
        ],
        "groups": [
          {
            "display_name": "Data Rescue Events",
            "description": "",
            "image_display_url": "",
            "title": "Data Rescue Events",
            "id": "7e6363ef-35ed-43a2-ab20-d64df0cd421b",
            "name": "data-rescue-events"
          }
        ],
        "license_id": "other-pd",
        "relationships_as_subject": [],
        "organization": {
          "description": "The National Oceanic and Atmospheric Administration is an American scientific agency within the United States Department of Commerce focused on the conditions of the oceans and the atmosphere. NOAA warns of dangerous weather, charts seas, guides the use and protection of ocean and coastal resources, and conducts research to improve understanding and stewardship of the environment.",
          "created": "2017-02-15T13:10:32.467584",
          "title": "National Oceanic and Atmospheric Administration",
          "name": "national-oceanic-and-atmospheric-administration",
          "is_organization": true,
          "state": "active",
          "image_url": "https://upload.wikimedia.org/wikipedia/commons/7/79/NOAA_logo.svg",
          "revision_id": "8a473808-c59f-499e-9cad-7c2622cb70fe",
          "type": "organization",
          "id": "65307de6-2b39-4173-be30-20254d9e664b",
          "approval_status": "approved"
        },
        "name": "april-21-2014-goes-r-science-seminars",
        "isopen": true,
        "url": "http://www.goes-r.gov/users/sci-sem/2014_04_21.html",
        "notes": "JPSS and GOES-R Activities Supporting 2013 Fire Outbreaks presentation",
        "owner_org": "65307de6-2b39-4173-be30-20254d9e664b",
        "extras": [],
        "title": "April 21, 2014 - GOES-R Science Seminars",
        "revision_id": "b6087abd-a198-43fd-ae20-36876eae796b"
      }
```

#### Step 3

We downloaded the bag zip from above and found this:

```
.
├── bag-info.txt
├── bagit.txt
├── data
│   └── 0c7a3f3a-4e9c-4c16-8964-cac95a5a6a55
│       ├── 0c7a3f3a-4e9c-4c16-8964-cac95a5a6a55.html
│       ├── 0c7a3f3a-4e9c-4c16-8964-cac95a5a6a55.json
│       ├── data
│       │   ├── JPSS_GOES-R_fire_Science Seminar.pdf
│       │   └── JPSS_GOES-R_fire_Science Seminar.pptx
│       └── tools
├── manifest-md5.txt
└── tagmanifest-md5.txt

4 directories, 8 files
```

The `0c7a3f3a-4e9c-4c16-8964-cac95a5a6a55.json` file is the exact same as the one from `datarefuge-json` (this is where we grabbed them from)

On archivers.space, we found our UUID: https://www.archivers.space/urls/0C7A3F3A-4E9C-4C16-8964-CAC95A5A6A55

It looks like this dataset is just a powerpoint and a pdf and and html. Double check the work!

Ultimately it looks like this is a static dataset that does not require scraping. Pick another one!
