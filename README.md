----------------------------------------Bare Minimum Background----------------------------------------

FHIR Resource's are JSON representations of personal healthcare information (PHI).

FHIR resources are split into categories based on the data they transmit. 
There is a Medication type resource used to transmit medical data, 
a Procedure type resource used to transmit procedure data, 
a FamilyMedicalHistory resource used to transmit family medical history data. 

In total, there are currently 146 different types of resources being used.

Why do we have different resource types?

It enables electronic medical record (EMR) systems to organize, manage, and transport their data more easily. 

FHIR is also referred to as HL7 V4. Right now, a majority of US hospitals use either HL7 V2 (Pipe Delimited) 
or HL7 V3 (XML Based) to manage their data requirements

FHIR means Fast Healthcare Interoperability Resource. ATM Machine.

FHIR's advantages come in its ability to transport data in the relatively lightweight format of JSON.

FHIR using JSON allows much easier application development and integration with common web-frameworks.

There is a lot to add in this. I will try to get around to it.

DSTU Explanation
Bundles
Data Elements


----------------------------------------PROGAM----------------------------------------

This is a simple web scraper written in Python.

This program converts the FHIR Standards website into an API.

First, this program scrapes the index page for the FHIR website: https://www.hl7.org/fhir/resourcelist.html
This build a list of all the FHIR resources, defining their group, category, name, definition, and url.

The url of each FHIR resource redirects you to the resources page.

For example - https://www.hl7.org/fhir/allergyintolerance.html

This webpage contains the schema of each FHIR Resource, expressed in multiple formats.

We scrape the web pages for each of the resource returned from the index page. 

For reach resource, we create one sqlite table (all within the same database), and one csv table.
We store the csv files in their own directory, while keeping the sqlite database in the root directory.