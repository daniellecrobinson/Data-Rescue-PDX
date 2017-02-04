# [Data-Rescue-PDX](http://calagator.org/events/1250471401)

Volunteers! Welcome and thank you for spending your evening with us.

## Background
### Major players
- Data.gov - basically an repository of the consistent metadata - "it's just the phone book, not the actual houses."
- [DataRefuge](https://www.datarefuge.org/)(UPENN) - committed to making citable copies with clearly documented chains of custody, so let's help with that. 
- Internet archive & archive team - basically a hard drive, doing wayback machine for all nominated websites BUT it's just a crawl, it will miss a lot of data because the bots are dumb
- UC system - a bunch of simultaneous projects on storing and archiving data
 - California Digital Library - another harddrive, but with metadata expertise
 - UC Riverside - Azimuth data rescue project
 - UC Davis - **Climate-mirror** data rescue project
- Wider Community Involvent
 - You're now part of a multi-city, multi-institutal effort to catalog and archive data
   
### The issue with archiving data isn't storage space, it's metadata and curation

What's metadata? 

- Information about a data set.
- Makes the dataset useful, reusable, discoverable

Our job tonight is to find the raw data files online and make sure that they have good metadata.

- Who created the data set, when it was created, where it lives, what it contains, etc.
- Citable copies = discoverable! So your copy can be found and used by others, for instance on the Internet Archive.
- Clearly documented chains of custody = To prove that your copy is the same data as the original, so you want to reference the webpage that you found it on and data.gov metatdata ID to link back to where you found the data.

Metadata is super important -- it essentially makes data discovery and resuse possible -- and if all you do today is create metadata files, or find a few files that need metadata, that is AWESOME and necessary!

We have a job for you!

- Trainees - learn about JSON metadata, then join the Detectives
- Data Detectives - adopt a dataset, learn about it, make a JSON metadata file, add it to our list
- Super Hackers - automate downloading and build tools!

At this hackathon we'll be focusing on the [Climate Mirror](https://github.com/climate-mirror/how-to-help) effort.
Here are the [Climate Mirror Datasets](https://github.com/climate-mirror/datasets/issues), each issue links out to a dataset.
  
### 1. Trainees: Working with [JSON](http://www.json.org/) to make [Data.gov](https://www.data.gov/about)-friendly metadata

- JSON (JavaScript Object Notation) is: Language-independent way to organize information so that humans and machines can read it!
- "Agencies are required to publish a list of their data assets that are public, or could be made public. This list is made available as a data.json file hosted at the primary domain of the agency."
- So, working with the JSON files, we can see what public datasets exist.
- If a dataset exists without a JSON 

Take some time with this guide to [JSON Lines](https://github.com/jsonlines/guide) to familiarize yourself with Data.gov's metadata format (data.json). This guide will help you:

1. Download tools you'll need to play around with JSON files
2. Work in the command line with JSON Lines Command Line Interface (CLI) Tools 
3. If you've never worked in the terminal before - don't panic! 
  - This will be fun! This is your crash course! 
  - Here's a [CLI cheatsheet](https://github.com/daniellecrobinson/terminal-mac-cheatsheet), and | is a [pipe](https://en.wikipedia.org/wiki/Pipeline_(Unix))!
  - You'll do great! Ask for help when you get stuck :)

OK, now that you've run through that, you should feel more comfortable sorting through a JSON file for information about dataset contents, ownership, licensing, size, and other important info.

### 2. Data Detectives: Discovering data and creating JSON metadata files

Here is a sample exercise to take you through creating a metadata file.

Example: find a file with missing metadata?

 
 

  - Let's make a JSON file that includes all the information, including URLs to all the annual reports.
  - Here's the JSON file I made!
  
Here is a sample exercise to take you through creating a metadata file.

1. Adopt a dataset from [Climate-mirror](https://github.com/climate-mirror/datasets/issues) and check it out and pick a URL to work on.
 - Criteria: 
  - Is the URL to a server with a bunch of datasets or one specific dataset?
  - Is it clear what scientific purpose this dataset serves?
  - What organization funded it? Federally funded research?
  - Is raw data at the URL or is it a landing page where you need to click through? 
    > We want the metadata to be for raw data

 - **Example:** https://github.com/climate-mirror/datasets/issues/298
  - Here's the readme: https://www1.ncdc.noaa.gov/pub/data/annualreports/readme.txt
  - Let's pick one of the annual reports! https://www1.ncdc.noaa.gov/pub/data/
  - What are these? https://www1.ncdc.noaa.gov/pub/data/annualreports/
  - It's a bunch of these! https://www1.ncdc.noaa.gov/pub/data/annualreports/2013-annual.pdf 
 
2. Check whether your dataset exisits in other places - search for the URL that was reported to Climate-mirror.
 - Data.gov
 - IA.org
 - GitHub
 - Google - does anythign else point or link to your data?
 Does it exist in other locations? Does it have metadata?
 
  - **Example:** 
   - Google things! make sure it's in double "" so it's an exact match
    - "www1.ncdc.noaa.gov" annual reports - e.g. "server" + keywords - we found other annual reports! But not ours
    - "www1.ncdc.noaa.gov/pub/data/annualreports/" - we found only a UK Met office PDF citing our PDFs!
  
3. What's the status of the metadata?
 If you find metadata, grab it and paste in to a text file. 
 If not we are going to create it i a text file using a JSON template
  Create new metadata file in JSON format, help on the formatting [here](https://project-open-data.cio.gov/v1.1/metadata-resources/) and [here](https://project-open-data.cio.gov/v1.1/schema/dataset.json)
4. [Create issue](https://github.com/daniellecrobinson/Data-Rescue-PDX/issues) on leave comment on issue with link to data or metadata

    
More on Data.gov Metadata, including long lists of possible Dataset Field titles [here](https://project-open-data.cio.gov/v1.1/schema/)

Google also recently did a great post about using the Data.gov metadata format for discovery of datasets: https://research.googleblog.com/2017/01/facilitating-discovery-of-public.html

Is your data set missing form Data.gov? [Max](https://github.com/maxogden) has been working with them to produce a full copy of their metadata archive and a process for [reporting missing data](https://www.data.gov/developers/archiving)


## When you're ready to go




$ head data.json | jsonmap "{name: this.name, organization: this.organization.name, notes: this.notes.slice(0,60)}" 
$ cat data.json | jsonmap "{name: this.name, organization: this.organization.name, notes: this.notes.slice(0,60)}"

[DataRescue Harvester](http://www.ppehlab.org/datarescue-harvester)
[DataRescue Seeder](https://www.ppehlab.org/datarescue-seeders)
[DataRescue Checker, Bagger, Describer](http://www.ppehlab.org/datarescue-describersplus)
