# [Data-Rescue-PDX](http://calagator.org/events/1250471401)
https://www.facebook.com/events/1891777784386985/

Volunteers! Welcome and thank you for spending your evening with us.

[DataRefuge](http://www.ppehlab.org/) is committed to making citable copies with clearly documented chains of custody - so let's help with that. 

- Citable copies = discoverable! So your copy can be found and used by others, for instance on the Internet Archive
- Clearly documented chains of custody = To prove that your copy is the same data as the original, so you want to reference the webpage that you found it on and data.gov metatdata ID to link back to where you found the data.

We have a job for you!
[DataRescue Harvester](http://www.ppehlab.org/datarescue-harvester)
[DataRescue Seeder](https://www.ppehlab.org/datarescue-seeders)
[DataRescue Checker, Bagger, Describer](http://www.ppehlab.org/datarescue-describersplus)


## Background

At this hackathon we'll be focusing on the [Climate Mirror](https://github.com/climate-mirror/how-to-help) effort.
Here are the [Climate Mirror Datasets](https://github.com/climate-mirror/datasets/issues), each issue links out to a dataset
  
### 1. [Data.gov](https://www.data.gov/about)

 - "Agencies are required to publish a list of their data assets that are public, or could be made public. This list is made available as a data.json file hosted at the primary domain of the agency."
 - So, working with the JSON files, we can see what public datasets exist.
 
### 2. Working with [JSON](http://www.json.org/)

 - Language-independent way to organize information so that humans and machines can read it!
 - JavaScript Object Notation
 - data-interchange format fo text-only data 

Take some time with this guide to [JSON Lines](https://github.com/jsonlines/guide) to familiarize yourself with Data.gov's metadata format (data.json). This guide will help you:

1. Download tools you'll need to play around with JSON files
2. Work in the command line with JSON Lines Command Line Interface (CLI) Tools 
3. If you've never worked in the terminal before - don't panic! 
  - This will be fun! This is your crash course! 
  - Here's a [CLI cheatsheet](https://github.com/daniellecrobinson/terminal-mac-cheatsheet), and | is a [pipe](https://en.wikipedia.org/wiki/Pipeline_(Unix))!
  - You'll do great! Ask for help when you get stuck :)

OK, now that you've run through that, you should feel more comfortable sorting through a JSON file for information about dataset contents, ownership, licensing, size, and other important info.

### 3. Creating a JSON metadata file [NEEDS WORK]

Metadata is super important -- it essentially makes data discovery and resuse possible -- and if all you do today is create metadata files, or find a few files that need metadata, that is AWESOME and necessary!

Here is a sample exercise to take you through creating a metadata file.

1. Step 1, find a file with missing metadata?
  check that the domain exisits on Data.gov
  - Example: https://github.com/climate-mirror/datasets/issues/298
  - Here's the readme: https://www1.ncdc.noaa.gov/pub/data/annualreports/readme.txt
  - Let's pick one of the anual reports! https://www1.ncdc.noaa.gov/pub/data/
  - What are these? https://www1.ncdc.noaa.gov/pub/data/annualreports/
  - It's a bunch of these! https://www1.ncdc.noaa.gov/pub/data/annualreports/2013-annual.pdf  
  
  google URL - does anythign else point here?
  Does anything link to here?
  
2. create new metadata file in JSON format?
  
3. help on the formatting [here](https://project-open-data.cio.gov/v1.1/metadata-resources/) and [here](https://project-open-data.cio.gov/v1.1/schema/dataset.json)
4. Done?
5. Machine readable intititional ID
  
More on Data.gov Metadata, including long lists of possible Dataset Field titles [here](https://project-open-data.cio.gov/v1.1/schema/)

Google also recently did a great post about using the Data.gov metadata format for discovery of datasets: https://research.googleblog.com/2017/01/facilitating-discovery-of-public.html



## When you're ready to go

1. Adopt a dataset from [Climate-mirror](https://github.com/climate-mirror/datasets/issues)
2. Find out who, if anyone, has a copy of it. [more details here]
3. Look for a metadata file [MORE DETAILS HERE].
4. If it does not have a metadata file created for it, create one!
5. Check if your dataset and/or its associted metadata are on Data.gov, if not report it as a unlisted dataset

Is your data set missing form Data.gov? [Max](https://github.com/maxogden) has been working with them to produce a full copy of their metadata archive and a process for [reporting missing data](https://www.data.gov/developers/archiving)


$ head data.json | jsonmap "{name: this.name, organization: this.organization.name, notes: this.notes.slice(0,60)}" 
$ cat data.json | jsonmap "{name: this.name, organization: this.organization.name, notes: this.notes.slice(0,60)}"


