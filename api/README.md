# Using the Postman collection

The `SeedAspaceData.postman_collection.json` file provided in this directory 
can be used to seed a development instance of ArchivesSpace. 

## Collection Variables
The collection contains a number of **collection variables** that can/should be 
customized based on the developer's needs. The most relevant of these include:

| Variable                | Description                                  | Default |
| ----------------------- | -------------------------------------------- | ------- |
| ACCESSION_COUNT         | How many accessions to create                | 10      |
| AO_COUNT                | How many archival objects to create          | 10      |
| ASSESSMENT_COUNT        | How many assessments to create               | 10      |
| CLASSIFICATION_COUNT    | How many classifications to create           | 10      |
| CONTAINER_COUNT         | How many accessions to create                | 10      |
| CONTAINER_PROFILE_COUNT | How many container profiles to create        | 10      |
| DO_COUNT                | How many digital objects to create           | 10      |
| EVENT_COUNT             | How many events to create                    | 10      |
| LOCATION_COUNT          | How many locations to create                 | 10      |
| LOCATION_PROFILE_COUNT  | How many location profiles to create         | 10      |
| RESOURCE_COUNT          | How many resources to create                 | 10      |
| SUBJECT_TERMS           | An array of what types of subjects to create | `["cultural_context", "function", "genre_form", "geographic", "occupation", "style_period", "technique", "temporal", "topical", "uniform_title"]` |

## Environment 
The collection refers to three **environment variables** that will need to be 
set in a Postman environment prior to running the collection.  These include:

| Variable                | Description                                  |
| ----------------------- | -------------------------------------------- |
| ASPACE_BACKEND_URL      | API url                                      |
| USER                    | API username                                 |
| PW                      | Password for that API user                   |

For more information, see the [Postman docs](https://learning.postman.com/docs).

## Running the Collection
Once these variables are set, the some or all of the requests in the collection
may be run.  Again, refer to the most recent [Postman docs](https://learning.postman.com/docs)
for more guidance.