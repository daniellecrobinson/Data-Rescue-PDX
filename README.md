# [Data-Rescue-PDX](http://calagator.org/events/1250471401)

Volunteers! Welcome and thank you for spending your time with us.

This event is a volunteer effort to contribute to data back up efforts. By attending you agree to our Code of Conduct http://confcodeofconduct.com/ which we will enforce.

To chat after tonight, join the Science Hack PDX Slack: https://sciencepdxslackin.herokuapp.com/

### Citizen Science Metadata Curation Workshop!

There is curently no centralized storage and access system for scientific research datasets. Scientific data is scattered across the internet, where it may be deposited on hard to find servers without meaningful documentation to explain what the data is, who created it, the context in which it was created, and how it should be discovered and used by other researchers.

Throughout the DataRefuge community, many parallel efforts are working to ensure that important datasets are discovered, nominated for archiving, and safely backed up. However, many of the datasets in the archiving queue do not have machine the readable, standard metadata critical to the archiving process.

That's where you come in! We need your help to adopt one of these datasets, hopefully before they disappear from the web. Funding for science is uncertain, and datasets and the websites that accompany them could disappear at any time.

Your mission, if you choose to accept it (which you did implicitly by showing up and eating the pizza), is to create metadata and documentation for the scientific datasets that are being backed up by other DataRefuge efforts so that their existence and provenance is recorded into the online public record with standard, open metadata.

Your efforts will prevent these datasets from drifting into obscurity. A dataset without metadata can not be found, cited, or trusted by the scientific community. 

**Warning** You will be very confused for the first hour or so, because this is confusing. The data is all over the place, there are millions of files with no rhyme or reason. But fear not, everyone goes through this. We are all in this together! Before we continue, turn to your left (or right) and introduce yourself to the recruit Data Detective sitting next to you. When you get stuck, or have a question, they are your first point of contact (and you are theirs).

#### What is metadata? 

- Descriptive and/or machine readable information about a data set.
- Makes the dataset useful, reusable, discoverable.
- Good metadata is discoverable by search engines and uses open standards (today we focus on the JSON format, which is used by data.gov).

For example, a metadata file should address these questions:

- Who created the data set? 
- When was it created? 
- Is it being maintained? 
- Where was it downloaded form? 
- What types of data/How much data is in this dataset?
- Where did this data come from? 
- Is there a clearly documented chains of custody? 
- Can you prove that your copy is the same data as the original?

Metadata is super important -- it essentially makes data discovery and resuse possible -- and if all you do today is create metadata files, find metadata and match it to files that are being downloaded, or find a few files that need metadata, that is AWESOME and necessary!

### 2. Data Detectives: Discovering data and creating JSON metadata files

We have a job for you!

Here is the workflow you will be following:

1. Adopt a dataset from [Climate Mirror](https://github.com/climate-mirror/datasets/issues)
2. Claim your issue/dataset [in this spreadsheet](https://docs.google.com/spreadsheets/d/1Ojgw9-VFdwO2Qxrp9a6W6X8FFS4047uhvCf8Lw3Q6gU/edit?usp=sharing)
3. Research your dataset, discover or create metadata for it using a local text file
4. Finally, [create an issue in this repository](https://github.com/daniellecrobinson/Data-Rescue-PDX/issues) and leave comment on an issue with link to data or metadata, and/or add JSON metadata you created.

### Example

Here is a sample exercise to take you through the workflow

1. We need to adopt a dataset from [Climate-mirror](https://github.com/climate-mirror/datasets/issues). Visit the issues list and find one that nobody else has adopted yet.

**Example:** We're going to adopt this dataset: https://github.com/climate-mirror/datasets/issues/298. We've updated the Google Spreadsheet and are ready to dive in.

You might find after a few minutes that your dataset is incredibly confusing and hard to understand. This is normal. Here are some questions to ask during your research phase:

2. Is the URL to a server with a bunch of datasets or one specific dataset?

**Example** Our example issue linked to this server: https://www1.ncdc.noaa.gov/pub/data/. There seem to be dozens of datasets in many different folders. The folders seem to be about different scientific research topics. We've decided to pick the `annualreports` folder https://www1.ncdc.noaa.gov/pub/data/annualreports/ and ignore the rest of the folders on this server for now.

If you find a server hosting different scientific datasets in different folders, just start by picking one of them at random. Don't try to classify the entire server, let's just start small, other volunteers in the future will follow your trail and continue on the rest.

3. Is it clear what scientific purpose this dataset serves?

**Example** We opened one of the reports https://www1.ncdc.noaa.gov/pub/data/annualreports/2013-annual.pdf and it looks like this folder has a decades worth of NOAA NCDC Accomplishment Reports. Probably worth saving!

If you can't find out the purpose by clicking on the data, you should search the web for links to these files on Google to see how other people have used this data. See the [Google-Fu](#google-fu) section below.

4. What organization funded it? Federally funded research?

Sometimes this is in the URL of the server, or you might find it through googling different acronyms.

**Example** Our dataset is clearly from NOAA NCDC, which we learned in the PDFs as well as the server URL.

5. Is raw data at the URL or is it a landing page where you need to click through? 

*Raw data* is things like .CSV, .ZIP, .PDF or weird esoteric scientific data forms, usually displayed in a folder structure, and prompts you to Save As a download on your computer when you click on it. Raw data is sometimes hard to find.

A *landing page* is a HTML website that usually describes the research project and sometimes links to the raw data. If you find a landing page, try to find out where all the links to the raw data on the landing page(s) are.

**Example** We didn't have a landing page, just a link to the raw data. By searching Google for "www1.ncdc.noaa.gov/pub/data/annualreports/" we didn't find any landing page for these annual reports.

Since we're focusing on creating dataset metadata, we want to primarily find and describe the downloadable raw data, not only the project website or landing page (though the websites are useful for learning some about the dataset such as which agency created it etc.).
 
6. Check whether your dataset exists in other places - search for the URL that was reported to Climate-mirror.

Google-Fu comes in handy here! Someone might have already created metadata for this dataset. If the exact dataset you're working with is listed on Data.gov for example there will be a metadata JSON file already.

**Example** By searching Google for "www1.ncdc.noaa.gov/pub/data/annualreports/" we found out that the only other website on the internet that has linked to these reports is the UK Meterological Office. We did not find our dataset in any data repositories with metadata.

7. What's the status of the metadata?

- If you find metadata, you should inspect it! If it's JSON you can copy and paste in to [JSONLint](http://jsonlint.com/). This will format the file so you can read it. Then you can copy it into a local text editor to work with it some more. If you found JSON metadata, you might still be able to improve it. 

- If you are reasonably sure that the metadata you've found is describing the dataset you've adopted -- and nobody has linked to this metadata yet on the Climate Mirror issue -- leave a comment with a link to the metadata so others can benefit from your detective work! 
 
8. Editing or creating JSON metadata

- *If you found metadata in another form*, for example XML or even a README with a block of text, you can convert it to the JSON format.
- Take a look at this [JSON template](https://github.com/daniellecrobinson/Data-Rescue-PDX/blob/master/example.json). 
 - JSON organizes information about the data, the organization, and resources contained in the dataset. 
 - The example contains one a dataset with one resource, but multiple resources can be added when appropriate, see more examples in Max Ogden's [100 JSON files from Data.gov](https://github.com/jsonlines/guide/blob/master/datagov100.json)
 - More on metadata file in JSON formats, [more on metadata](https://project-open-data.cio.gov/v1.1/metadata-resources/) and [Schema](https://project-open-data.cio.gov/v1.1/schema/dataset.json)
- *If you didn't find any metadata*, you are going to create metadata in a text editor for your dataset using the [JSON template](https://github.com/daniellecrobinson/Data-Rescue-PDX/blob/master/example.json) as a guide.
- Notes on JSON:
 - It's fussy!
 - Mind all the . } and ]
 - Check your file in [JSONLint](http://jsonlint.com/) to verify that you have no syntax errors when you're done!

9. Post your metadata to the issue tracker

- TODO walk through posting the issue

## Google-Fu

- Search for a URL on only data.gov using Google: [`site:data.gov "www1.ncdc.noaa.gov/pub/data/annualreports/"`](https://www.google.com/search?q=site%3Adata.gov+%22www1.ncdc.noaa.gov%2Fpub%2Fdata%2Fannualreports%2F%22&oq=site%3Adata.gov+%22www1.ncdc.noaa.gov%2Fpub%2Fdata%2Fannualreports%2F%22&aqs=chrome..69i57j69i58.201j0j1&sourceid=chrome&ie=UTF-8)

 Google things! make sure it's in double "" so it's an exact match
 - "www1.ncdc.noaa.gov" annual reports (e.g. "*server*" + keywords) - we found other annual reports! But not ours
 - "www1.ncdc.noaa.gov/pub/data/annualreports/" - we found only a UK Met office PDF citing our PDFs!

**Extra Credit** 

More on metadata file in JSON formats, [more on metadata](https://project-open-data.cio.gov/v1.1/metadata-resources/) and [Schema](https://project-open-data.cio.gov/v1.1/schema/dataset.json)
    
More on Data.gov Metadata, including long lists of possible Dataset Field titles [here](https://project-open-data.cio.gov/v1.1/schema/)

Google also recently did a great post about using the Data.gov metadata format for discovery of datasets: https://research.googleblog.com/2017/01/facilitating-discovery-of-public.html

Is your data set missing form Data.gov? [Max](https://github.com/maxogden) has been working with them to produce a full copy of their metadata archive and a process for [reporting missing data](https://www.data.gov/developers/archiving)

[DataRescue Harvester](http://www.ppehlab.org/datarescue-harvester)
[DataRescue Seeder](https://www.ppehlab.org/datarescue-seeders)
[DataRescue Checker, Bagger, Describer](http://www.ppehlab.org/datarescue-describersplus)

Other places to look for your dataset
 - [Data.gov](https://www.data.gov/)
 - [Internet Archive](https://archive.org/index.php)
 - [GitHub](https://github.com/)
