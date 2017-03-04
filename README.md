# [Data-Rescue-PDX](http://calagator.org/events/1250471401)

Coming on Saturday 3/4/17? Register and get details of the rooms here: https://www.eventbrite.com/e/open-data-day-portland-tickets-31370043645

Volunteers! Welcome and thank you for spending your time with us.

Tools reguired: A laptop, curiosity, and a GitHub account. If you have never used GitHub - welcome! We will talk beginners through setting up GitHub accounts and the use of the platform. See our [Contributing Guide](https://github.com/daniellecrobinson/Data-Rescue-PDX/blob/master/CONTRIBUTING.md) for more information.

This event is a volunteer effort to contribute to data back up efforts. By attending you agree to our [Code of Conduct](https://github.com/daniellecrobinson/Data-Rescue-PDX/blob/master/CODE_OF_CONDUCT.md) which we will enforce.

To chat after this event, join the Science Hack PDX Slack: https://sciencepdxslackin.herokuapp.com/

### Citizen Science Metadata Curation Workshop!
### The basics: We have a job for you!

Here is the workflow you will be following:

1. **Adopt** a dataset from the `datarefuge-json` in this GitHub repo folder that nobody else has claimed yet
2. **Claim** your issue/dataset [in this spreadsheet](https://docs.google.com/spreadsheets/d/1Ojgw9-VFdwO2Qxrp9a6W6X8FFS4047uhvCf8Lw3Q6gU/edit#gid=1105874853).
3. **Research** your dataset to improve standard JSON formatted metadata using a local text file.
4. **Document** your dataset by [creating an issue in this repository](https://github.com/daniellecrobinson/Data-Rescue-PDX/issues) and using our issue template to add the JSON metadata you improved.
5. **Verify** metadata from two other contributors. 
6. **Repeat!**


### Background
There is curently no centralized storage and access system for scientific research datasets. Scientific data is scattered across the internet, where it may be deposited on hard to find servers without meaningful documentation to explain what the data is, who created it, the context in which it was created, and how it should be discovered and used by other researchers.

Throughout the DataRefuge community, many parallel efforts are working to ensure that important datasets are discovered, nominated for archiving, and safely backed up. However, many of the datasets in the archiving queue do not have machine the readable, standard metadata critical to the archiving process.

We've aggregated all the metadata that has been rescued and published at [DataRefuge.org](http://datarefuge.org/) and placed the metadata in the folder `datarefuge-json`. These are files created by the volunteer who backed up the data to DataRefuge in ["bags"](https://tools.ietf.org/html/draft-kunze-bagit-14), but we need to help them improve their metadata!

That's where you come in! We need your help to adopt one of these datasets, hopefully before they disappear from the web. Funding for science is uncertain, and datasets and the websites that accompany them could disappear at any time.

Your mission, if you choose to accept it (which you did implicitly by showing up and eating the snacks), is to improve metadata and documentation for the scientific datasets that are being backed up by other DataRefuge efforts so that their existence and provenance is recorded into the online public record with standard, open metadata.

Your efforts will prevent these datasets from drifting into obscurity. A dataset without metadata can not be found, cited, or trusted by the scientific community. 

**Warning:** You will be very confused for the first hour or so, because this is confusing. The data is all over the place, there are millions of files with no rhyme or reason. But fear not, everyone goes through this. We are all in this together! Before we continue, turn to your left (or right) and introduce yourself to the recruit Data Detective sitting next to you. When you get stuck, or have a question, they are your first point of contact (and you are theirs).

#### What is metadata? 

- Descriptive, standardized, machine readable information about a dataset.
- Makes the dataset useful, reusable, discoverable.
- Good metadata is discoverable by search engines and uses open standards (today we focus on the JSON format, which is used by Data.gov).

A good JSON metadata file should address these questions using [standard field codes](https://project-open-data.cio.gov/v1.1/metadata-resources/#field-mappings):

- Who created the data set? What agency, people, missions, or experiments does it relate to?
- Is it being maintained? 
- From where was it downloaded? (Landing page)
- What types of data are in this dataset?
- Are there publications associted with it?

**Example** This is the kind of machine-readable JSON file that humans are good at creating! Machines (people writing scrapers) will deal with the resources within each url, but people can extract extra detail about resource ownership, missions or experiments associted with the dataset, licensing, and notes. 

```
{
  "title": "VA National Formulary",
  "maintainer": "Don Lees",
  "maintainer_email": "Don.Lees@va.gov",
  "author": null,
  "author_email": null,
  "notes": "The VA National Formulary is a listing of products (drugs and supplies) that must be available for prescription at all VA facilities, and cannot be made non-formulary by a Veteran Integrated Service Network (VISN) or individual medical center. Regarding chemical or biological entities that by law must be submitted to the United States (U.S.) Food and Drug Administration (FDA) for pre-marketing approval, only those entities that actually have been approved by FDA using New Drug Application (NDA), Abbreviated New Drug Application (ANDA), or biologics license, may be added to the VA National Formulary.",
  "license_id": "cc-zero",
  "landingPage": "URL for landing page goes here ",
  "id": "ff9ae098-eccc-41d8-bfcd-5e8ed047db05",
  "doi":"publication or data doi",
  "isPartOf": "larger project?",
  "tags": "FDA",
  "organization": {
    "description": "",
    "title": "Department of Veterans Affairs",
    "name": "va-gov",
    "is_organization": true,
    "image_url": "https://raw.githubusercontent.com/GSA/logo/master/va.png",
    "type": "organization",
    "id": ""
  }
}
```
With appologies to EPA Enviornmental Justice Grant Programs, this is less-good metadata, machines can't easily read this.
  - Field codes are non-standard
  - Inconsistant capitalization, use of (), and _ 
  - Not properly JSON formatted
  - Multiple fields contain long strings of text (that belongs in notes)
```
{
	"Type(s) of datasets at resource url": "HTML landing page with map representing locations of EPA Environmental Justice Grant Programs. PDFs with more detail on EPA’s Environmental Justice Collaborative Problem-Solving Cooperative Agreement Program and the EPA’s Small Grants Projects.",
	"UUID": "82326781-CFFA-4007-AB66-CBF27C7993E3",
	"recommended_approach": ""
}
```

Machine readable metadata is super important -- it essentially makes data discovery and resuse possible -- and if all you do today is improve one metadata file for one dataset, or find metadata online and match it to a dataset that has been downloaded, or find a few datasets that need metadata, that is AWESOME and necessary! No contribution is too small!

### Data Detectives: Discovering data and creating JSON metadata files

We have a job for you!

Here is the workflow you will be following:

1. **Adopt** a dataset from the `datarefuge-json` folder that nobody else has claimed yet
2. **Claim** your issue/dataset [in this spreadsheet](https://docs.google.com/spreadsheets/d/1Ojgw9-VFdwO2Qxrp9a6W6X8FFS4047uhvCf8Lw3Q6gU/edit#gid=1105874853).
3. **Research** your dataset to improve standard JSON formatted metadata using a local text file.
4. **Document** your dataset by [creating an issue in this repository](https://github.com/daniellecrobinson/Data-Rescue-PDX/issues) and using our issue template to add the JSON metadata you improved.
5. **Verify** metadata from two other contributors. 
6. **Repeat!**

### Example

Here is a sample exercise to take you through the workflow

1. Adopt a dataset from the `datarefuge-json` folder. Each file in this folder has a ID as it's name. This ID comes from the [DataRefuge.org](https://datarefuge.org) repository. Search the google spreadsheet for your ID and URL before claiming your dataset Visit the issues list and find one that nobody else has adopted yet.  
**Example:** We're going to adopt this dataset: `datarefuge-json/D82A9773-81AF-4AF2-BF01-52CA2CF3BA22.json`. We've updated the Google Spreadsheet and are ready to dive in.  
You might find after a few minutes that your dataset is incredibly confusing and hard to understand. This is normal. Here are some questions to ask during your research phase:

2. Is the URL to a server with a bunch of datasets or one specific dataset?  
**Example:** Our example issue linked to this site: http://www.nrel.gov/gis/data_solar.html. There seem to be dozens of datasets on many topics. The folders seem to be about different scientific research topics. 
If you find a server hosting different scientific datasets in different folders or different links, that's fine. A high level JSON metadata file describing the page is useful, you don't need to list 3000 resources. Do what you can. Do what humans are good at! Like figurign out whether something is science (does it have a publication with a DOI?) and figuring out whether people can use it (digging up the license information). 

3. Is it clear what scientific purpose this dataset serves?  
**Example:**  http://www.nrel.gov/gis/data_solar.htm - "These data provides monthly average and annual average daily total solar resource averaged over surface cells of 0.1 degrees in both latitude and longitude, or about 10 km in size. This data was developed using the State University of New York/Albany satellite radiation model. This model was developed by Dr. Richard Perez and collaborators at the National Renewable Energy Laboratory and other universities for the U.S. Department of Energy."  Probably worth saving!  
If you can't find out the purpose by clicking on the data, you should search the web for links to these files on Google to see how other people have used this data. See the [Google-Fu](#google-fu) section below.

4. What organization funded it? Federally funded research?  
Sometimes this is in the URL of the server, or you might find it through googling different acronyms.  
**Example:** Our dataset is clearly from National Renewable Energy Laboratory (NREL), which we learned in the URL.

5. Is raw data at the URL or is it a landing page where you need to click through?   
*Raw data* is things like .CSV, .ZIP, .PDF or weird esoteric scientific data forms, usually displayed in a folder structure, and prompts you to Save As a download on your computer when you click on it. Raw data is sometimes hard to find.  
A *landing page* is a HTML website that usually describes the research project and sometimes links to the raw data. If you find a landing page, try to find out where all the links to the raw data on the landing page(s) are.  
**Example:** This is a landing page that links out to multiple datasets.  
Since we're focusing on creating dataset metadata, we want to primarily find and describe the downloadable raw data, not only the project website or landing page (though the websites are useful for learning some about the dataset such as which agency created it etc.).
 
6. Check whether your dataset exists in other places - search for the URL.  
*Google-Fu* (see below) comes in handy here! Someone might have already created metadata for this dataset. If the exact dataset you're working with is listed on Data.gov for example there will be a metadata JSON file already.  
**Example:** By searching Google for "http://www.nrel.gov/gis/data/GIS_Data_Technology_Specific/United_States/Solar" we found out that this URL is really the only place on the internet that links to these datasets. We can check the URLs of the raw data files that link out from this site, and we did not find our dataset in any data repositories (with/without metadata). 
**This means that if this webpage disappears, these datasets will be super hard to find** Though, this dataset has been crawled by the Internet Archive, so it's going to be OK!

7. What's the status of the metadata?  
If you find metadata, you should inspect it! If it's JSON you can copy and paste in to [JSONLint](http://jsonlint.com/). This will format the file so you can read it. Then you can copy it into a local text editor to work with it some more. If you found JSON metadata, you might still be able to improve it.   
I'm going to try to make a bot that checks your GitHub Issues tomorrow, so watch out for the bot!
If you are reasonably sure that the metadata you've found is describing the dataset you've adopted -- and nobody has linked to this metadata yet -- leave a comment with a link to the metadata so others can benefit from your detective work! 
**Example:** Our example is a landing page with multiple links to download data. Files have XML metadata, which is good but this dataset needs a JSON file that describes its ownership, contents, and other key details. So let's make one!
 
8. Editing or creating JSON metadata  
*If you found metadata in another form*, for example XML or even a README with a block of text, you can convert it to the JSON format using a converter or creating a file by hand in a text editor.
Take a look at this [JSON template](https://github.com/daniellecrobinson/Data-Rescue-PDX/blob/master/example.json). 

- JSON organizes information about the data, the organization, and resources contained in the dataset. 
- The example contains one a dataset with multiple resources, see more examples in Max Ogden's [100 JSON files from Data.gov](https://github.com/jsonlines/guide/blob/master/datagov100.json) - but don't worry about the resoures, scrapers will get resources. Huamns are better at finding extra details like licenses.
 - More on metadata file in JSON formats, [more on metadata](https://project-open-data.cio.gov/v1.1/metadata-resources/) and [Schema](https://project-open-data.cio.gov/v1.1/schema/dataset.json)
- *To improve your metadata*, you are going to edit your metadata in a text editor for your dataset using the [JSON template](https://github.com/daniellecrobinson/Data-Rescue-PDX/blob/master/example-2.json) as a guide. Focus on collecting info that humans are good at getting, like mission/experiment, licensing, and other details that may be hidden.

- **Notes on JSON**:
 - ["Pretty print" it](http://jsonprettyprint.com/) if you found it formatted as a block or long line
 - It's fussy! I had to check my JSON 3 times before I found an errant ", was throwing it off
 - Mind placement of all the . } and ]
 - Check your file in [JSONLint](http://jsonlint.com/) to verify that you have no syntax errors when you're done!
 
 Use your favorite text editor 
 ![screenshot](https://github.com/daniellecrobinson/Data-Rescue-PDX/blob/master/Screenshot_SolarData_JSON.png)

```
{
  "title": "Solar Data, 10-kilometer",
  "maintainer": "National Renewable Energy Lab (NREL)",
  "maintainer_email": "GDS@nrel.gov",
  "author": "GIS at NREL",
  "author_email": "GDS@nrel.gov",
  "notes": "This data provides monthly average and annual average daily total solar resource averaged over surface cells of 0.1 degrees in both latitude and longitude, or about 10 km in size. This data was developed using the State University of New York/Albany satellite radiation model. This model was developed by Dr. Richard Perez and collaborators at the National Renewable Energy Laboratory and other universities for the U.S. Department of Energy. See http://www.nrel.gov/disclaimer.html for reuse restrictions.",
  "license_id": "restricted",
  "landingPage": "http://www.nrel.gov/gis/data_solar.html",
  "id": "D82A9773-81AF-4AF2-BF01-52CA2CF3BA22",
  "doi":"10.2172/1007346",
  "isPartOf": "Dynamic Maps, Geographic Information System (GIS) Data and Analysis Tools",
  "tags": "GIS",
  "organization": {
    "description": "NREL's Geospatial Data Science Team analyzes renewable energy resources and many other data sources to determine which energy technologies are viable solutions across the globe and inputs the data into a geographic information system.",
    "title": "National Renewable Energy Lab (NREL)",
    "name": "NREL",
    "is_organization": true,
    "image_url": "",
    "type": "organization",
    "id": "NREL GIS"
    }
}
```

9. **Document** your dataset by [creating an issue in this repository](https://github.com/daniellecrobinson/Data-Rescue-PDX/issues) and using our issue template to add the JSON metadata you found or created. Post your metadata to the issue tracker

10. **Verify** metadata from two other contributors. Open an issue, check the metadata by asking the following questions:
 -Is the dataset URL correct?
 -Is the dataset UUID correct?
 -Are the ownership details of the datset correct?
 -Is the JSON file formatted corrently? Check it in [JSONLint](http://jsonlint.com/), mind those extra spaces!
 **Any other key questions to ask?**
 
## Let's all try it! Beginners and those who need to set up GitHub accounts organize, and everyone else dives in.

## Google-Fu

Search for a URL on only data.gov using Google: [`site:data.gov "www1.ncdc.noaa.gov/pub/data/annualreports/"`](https://www.google.com/search?q=site%3Adata.gov+%22www1.ncdc.noaa.gov%2Fpub%2Fdata%2Fannualreports%2F%22&oq=site%3Adata.gov+%22www1.ncdc.noaa.gov%2Fpub%2Fdata%2Fannualreports%2F%22&aqs=chrome..69i57j69i58.201j0j1&sourceid=chrome&ie=UTF-8)

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
