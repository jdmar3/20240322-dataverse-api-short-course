# Create a collection and add a dataset

## Focus

This section is intended to get us oriented in two ways:

1. Learn how to breakdown and build up the parts of an HTTP request in `httr2`
2. Use this technique to build requests in Dataverse to create collections and upload data

## Useful links

Installing HTTR2

https://rbasics.org/guides/how-to-use-the-httr2-package-in-r/

HTTR2 Documentation

https://httr2.r-lib.org/articles/httr2.html

Getting Data through APIs - David Gerard

https://data-science-master.github.io/lectures/05_web_scraping/05_apis.html#authentication

## EXAMPLES

### View collection with httr2

```R
# Check if the package is installed
if (!require("httr2","httpuv","jsonlite")) {
  # Install the package if it's not already installed
  install.packages(c("httr2","httpuv","jsonlite"))
}

# Load the package
library("httr2","httpuv","jsonlite")

# View Collection
# Setting up variables
server_url <- "https://demo.dataverse.org"
id <- "tb12"
endpoint <-"/api/dataverses"
# Create base request
base_req <- request(server_url)
# Create the full request
view_dataverse_collection <- req_url_path_append(base_req, endpoint, id)
#Performing a dry
req_dry_run(view_dataverse_collection)
# Make the request
collection_out <- req_perform(view_dataverse_collection)
# Look at data
resp_body_json(collection_out)
```

### Request

```

```

```json
{
  "status": "OK",
  "data": {
    "id": 2067890,
    "identifier": "FK2/YAAX1R",
    "persistentUrl": "https://doi.org/10.70122/FK2/YAAX1R",
    "protocol": "doi",
    "authority": "10.70122",
    "publisher": "Demo Dataverse",
    "publicationDate": "2023-06-05",
    "storageIdentifier": "s3://10.70122/FK2/YAAX1R",
    "latestVersion": {
      "id": 233980,
      "datasetId": 2067890,
      "datasetPersistentId": "doi:10.70122/FK2/YAAX1R",
      "storageIdentifier": "s3://10.70122/FK2/YAAX1R",
      "versionNumber": 1,
      "versionMinorNumber": 0,
      "versionState": "RELEASED",
      "UNF": "UNF:6:iSz38eRfzxPv54AKU42WGA==",
      "lastUpdateTime": "2023-06-05T14:33:16Z",
      "releaseTime": "2023-06-05T14:33:16Z",
      "createTime": "2023-06-05T13:18:44Z",
      "publicationDate": "2023-06-05",
      "citationDate": "2023-06-06",
      "license": {
        "name": "CC0 1.0",
        "uri": "http://creativecommons.org/publicdomain/zero/1.0",
        "iconUri": "https://licensebuttons.net/p/zero/1.0/88x31.png"
      },
      "termsOfAccess": "Send an email to xxxxx@cccc.edu",
      "fileAccessRequest": true,
      "metadataBlocks": {
        "citation": {
          "displayName": "Citation Metadata",
          "name": "citation",
          "fields": [
            {
              "typeName": "title",
              "multiple": false,
              "typeClass": "primitive",
              "value": "A survey on teenage pregnancies in Taiwan"
            },
            {
              "typeName": "author",
              "multiple": true,
              "typeClass": "compound",
              "value": [
                {
                  "authorName": {
                    "typeName": "authorName",
                    "multiple": false,
                    "typeClass": "primitive",
                    "value": "Waithira, Naomi"
                  },
                  "authorAffiliation": {
                    "typeName": "authorAffiliation",
                    "multiple": false,
                    "typeClass": "primitive",
                    "value": "MORU"
                  },
                  "authorIdentifierScheme": {
                    "typeName": "authorIdentifierScheme",
                    "multiple": false,
                    "typeClass": "controlledVocabulary",
                    "value": "ORCID"
                  },
                  "authorIdentifier": {
                    "typeName": "authorIdentifier",
                    "multiple": false,
                    "typeClass": "primitive",
                    "value": "242454522444222"
                  }
                }
              ]
            },
            {
              "typeName": "datasetContact",
              "multiple": true,
              "typeClass": "compound",
              "value": [
                {
                  "datasetContactName": {
                    "typeName": "datasetContactName",
                    "multiple": false,
                    "typeClass": "primitive",
                    "value": "Waithira, Naomi"
                  },
                  "datasetContactEmail": {
                    "typeName": "datasetContactEmail",
                    "multiple": false,
                    "typeClass": "primitive",
                    "value": "naomi@tropmedres.ac"
                  }
                }
              ]
            },
            {
              "typeName": "dsDescription",
              "multiple": true,
              "typeClass": "compound",
              "value": [
                {
                  "dsDescriptionValue": {
                    "typeName": "dsDescriptionValue",
                    "multiple": false,
                    "typeClass": "primitive",
                    "value": "A survey on teenage pregnancies in Taiwan"
                  }
                }
              ]
            },
            {
              "typeName": "subject",
              "multiple": true,
              "typeClass": "controlledVocabulary",
              "value": [
                "Medicine, Health and Life Sciences"
              ]
            },
            {
              "typeName": "keyword",
              "multiple": true,
              "typeClass": "compound",
              "value": [
                {
                  "keywordValue": {
                    "typeName": "keywordValue",
                    "multiple": false,
                    "typeClass": "primitive",
                    "value": "Pregnancy"
                  },
                  "keywordVocabulary": {
                    "typeName": "keywordVocabulary",
                    "multiple": false,
                    "typeClass": "primitive",
                    "value": "MeSH"
                  }
                }
              ]
            },
            {
              "typeName": "depositor",
              "multiple": false,
              "typeClass": "primitive",
              "value": "Waithira, Naomi"
            },
            {
              "typeName": "dateOfDeposit",
              "multiple": false,
              "typeClass": "primitive",
              "value": "1986-06-05"
            }
          ]
        }
      },
      "files": [
        {
          "label": "0MANIFEST.TXT",
          "restricted": false,
          "version": 1,
          "datasetVersionId": 233980,
          "dataFile": {
            "id": 2067895,
            "persistentId": "doi:10.70122/FK2/YAAX1R/RK2WS3",
            "pidURL": "https://doi.org/10.70122/FK2/YAAX1R/RK2WS3",
            "filename": "0MANIFEST.TXT",
            "contentType": "text/plain",
            "friendlyType": "Plain Text",
            "filesize": 482,
            "embargo": {
              "dateAvailable": "2023-06-06",
              "reason": "Just :)"
            },
            "storageIdentifier": "s3://demo-dataverse-org:1888bb3b05f-08187fa0100c",
            "rootDataFileId": -1,
            "md5": "1ccbb76fc6bfe3f323b07949db01a42f",
            "checksum": {
              "type": "MD5",
              "value": "1ccbb76fc6bfe3f323b07949db01a42f"
            },
            "tabularData": false,
            "creationDate": "2023-06-05",
            "publicationDate": "2023-06-05",
            "fileAccessRequest": true
          }
        },
        {
          "label": "BarChart.jpg",
          "restricted": false,
          "version": 1,
          "datasetVersionId": 233980,
          "dataFile": {
            "id": 2067900,
            "persistentId": "doi:10.70122/FK2/YAAX1R/Q3DFLV",
            "pidURL": "https://doi.org/10.70122/FK2/YAAX1R/Q3DFLV",
            "filename": "BarChart.jpg",
            "contentType": "image/jpeg",
            "friendlyType": "JPEG Image",
            "filesize": 339679,
            "storageIdentifier": "s3://demo-dataverse-org:1888bb3b058-f1b6709a31d5",
            "rootDataFileId": -1,
            "md5": "e114c017c20b68fc568fe5efce692946",
            "checksum": {
              "type": "MD5",
              "value": "e114c017c20b68fc568fe5efce692946"
            },
            "tabularData": false,
            "creationDate": "2023-06-05",
            "publicationDate": "2023-06-05",
            "fileAccessRequest": true
          }
        },
        {
          "label": "Dataverse Community Meeting, 2023 Dataverse Workshop.pdf",
          "restricted": false,
          "version": 1,
          "datasetVersionId": 233980,
          "dataFile": {
            "id": 2067892,
            "persistentId": "doi:10.70122/FK2/YAAX1R/UMFJRJ",
            "pidURL": "https://doi.org/10.70122/FK2/YAAX1R/UMFJRJ",
            "filename": "Dataverse Community Meeting, 2023 Dataverse Workshop.pdf",
            "contentType": "application/pdf",
            "friendlyType": "Adobe PDF",
            "filesize": 6684606,
            "storageIdentifier": "s3://demo-dataverse-org:1888bb3b02f-df36a4710053",
            "rootDataFileId": -1,
            "md5": "6fa8880d28c68b340a6a583986a2a6c7",
            "checksum": {
              "type": "MD5",
              "value": "6fa8880d28c68b340a6a583986a2a6c7"
            },
            "tabularData": false,
            "creationDate": "2023-06-05",
            "publicationDate": "2023-06-05",
            "fileAccessRequest": true
          }
        },
        {
          "label": "ImageChart.png",
          "restricted": false,
          "version": 1,
          "datasetVersionId": 233980,
          "dataFile": {
            "id": 2067896,
            "persistentId": "doi:10.70122/FK2/YAAX1R/YOAAWK",
            "pidURL": "https://doi.org/10.70122/FK2/YAAX1R/YOAAWK",
            "filename": "ImageChart.png",
            "contentType": "image/png",
            "friendlyType": "PNG Image",
            "filesize": 56083,
            "storageIdentifier": "s3://demo-dataverse-org:1888bb3afd3-8356bf1cf128",
            "rootDataFileId": -1,
            "md5": "754f0d3a9923c34af78e3493f010382b",
            "checksum": {
              "type": "MD5",
              "value": "754f0d3a9923c34af78e3493f010382b"
            },
            "tabularData": false,
            "creationDate": "2023-06-05",
            "publicationDate": "2023-06-05",
            "fileAccessRequest": true
          }
        },
        {
          "label": "MANIFEST.TXT",
          "restricted": false,
          "version": 1,
          "datasetVersionId": 233980,
          "dataFile": {
            "id": 2067898,
            "persistentId": "doi:10.70122/FK2/YAAX1R/FQQFSE",
            "pidURL": "https://doi.org/10.70122/FK2/YAAX1R/FQQFSE",
            "filename": "MANIFEST.TXT",
            "contentType": "text/plain",
            "friendlyType": "Plain Text",
            "filesize": 353,
            "storageIdentifier": "s3://demo-dataverse-org:1888bb3afdc-a0e124701ef6",
            "rootDataFileId": -1,
            "md5": "5be18668d245d7924ce508a4c9d22c7c",
            "checksum": {
              "type": "MD5",
              "value": "5be18668d245d7924ce508a4c9d22c7c"
            },
            "tabularData": false,
            "creationDate": "2023-06-05",
            "publicationDate": "2023-06-05",
            "fileAccessRequest": true
          }
        },
        {
          "label": "Test Data Alpha.tab",
          "restricted": true,
          "version": 4,
          "datasetVersionId": 233980,
          "dataFile": {
            "id": 2067894,
            "persistentId": "doi:10.70122/FK2/YAAX1R/6EDMGV",
            "pidURL": "https://doi.org/10.70122/FK2/YAAX1R/6EDMGV",
            "filename": "Test Data Alpha.tab",
            "contentType": "text/tab-separated-values",
            "friendlyType": "Tab-Delimited",
            "filesize": 6394,
            "storageIdentifier": "s3://demo-dataverse-org:1888bb3b05d-21d9c0aec290",
            "originalFileFormat": "application/x-stata",
            "originalFormatLabel": "Stata Binary",
            "originalFileSize": 9090,
            "originalFileName": "Test Data Alpha.dta",
            "UNF": "UNF:6:Iav+suqRnjXHbcZOlOxueQ==",
            "rootDataFileId": -1,
            "md5": "faeb19ec96a34523e4fd0defea0cebda",
            "checksum": {
              "type": "MD5",
              "value": "faeb19ec96a34523e4fd0defea0cebda"
            },
            "tabularData": true,
            "creationDate": "2023-06-05",
            "publicationDate": "2023-06-05",
            "fileAccessRequest": true
          }
        },
        {
          "label": "Test Data Beta.tab",
          "restricted": false,
          "version": 3,
          "datasetVersionId": 233980,
          "dataFile": {
            "id": 2067899,
            "persistentId": "doi:10.70122/FK2/YAAX1R/ECU9CZ",
            "pidURL": "https://doi.org/10.70122/FK2/YAAX1R/ECU9CZ",
            "filename": "Test Data Beta.tab",
            "contentType": "text/tab-separated-values",
            "friendlyType": "Tab-Delimited",
            "filesize": 35441,
            "storageIdentifier": "s3://demo-dataverse-org:1888bb3afda-f45ffc2d0b7b",
            "originalFileFormat": "application/x-stata",
            "originalFormatLabel": "Stata Binary",
            "originalFileSize": 31175,
            "originalFileName": "Test Data Beta.dta",
            "UNF": "UNF:6:y5lOy2RfMHvDW3OeIDYgYQ==",
            "rootDataFileId": -1,
            "md5": "ba1fb8e3b8c77c5ab09a6d88a82d3ed9",
            "checksum": {
              "type": "MD5",
              "value": "ba1fb8e3b8c77c5ab09a6d88a82d3ed9"
            },
            "tabularData": true,
            "creationDate": "2023-06-05",
            "publicationDate": "2023-06-05",
            "fileAccessRequest": true
          }
        },
        {
          "label": "Test Document 1.pdf",
          "restricted": false,
          "version": 1,
          "datasetVersionId": 233980,
          "dataFile": {
            "id": 2067893,
            "persistentId": "doi:10.70122/FK2/YAAX1R/YCYBQC",
            "pidURL": "https://doi.org/10.70122/FK2/YAAX1R/YCYBQC",
            "filename": "Test Document 1.pdf",
            "contentType": "application/pdf",
            "friendlyType": "Adobe PDF",
            "filesize": 40226,
            "storageIdentifier": "s3://demo-dataverse-org:1888bb3b052-bc5975fb71bd",
            "rootDataFileId": -1,
            "md5": "4b2680b30fda5d346d6876b4a11986a2",
            "checksum": {
              "type": "MD5",
              "value": "4b2680b30fda5d346d6876b4a11986a2"
            },
            "tabularData": false,
            "creationDate": "2023-06-05",
            "publicationDate": "2023-06-05",
            "fileAccessRequest": true
          }
        },
        {
          "label": "Test Document 2.docx",
          "restricted": false,
          "version": 1,
          "datasetVersionId": 233980,
          "dataFile": {
            "id": 2067897,
            "persistentId": "doi:10.70122/FK2/YAAX1R/HPK7DS",
            "pidURL": "https://doi.org/10.70122/FK2/YAAX1R/HPK7DS",
            "filename": "Test Document 2.docx",
            "contentType": "application/vnd.openxmlformats-officedocument.wordprocessingml.document",
            "friendlyType": "MS Word",
            "filesize": 15873,
            "storageIdentifier": "s3://demo-dataverse-org:1888bb3afe2-b089b6cea559",
            "rootDataFileId": -1,
            "md5": "4d5461be9dc4b76be0bb046a62b53340",
            "checksum": {
              "type": "MD5",
              "value": "4d5461be9dc4b76be0bb046a62b53340"
            },
            "tabularData": false,
            "creationDate": "2023-06-05",
            "publicationDate": "2023-06-05",
            "fileAccessRequest": true
          }
        }
      ]
    }
  }
}
```
