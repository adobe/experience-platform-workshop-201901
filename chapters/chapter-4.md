# 4. Ingest the Data

## Learning Objectives

- Learn how to ingest XDM-formatted data files
- Learn both the web UI and API interfaces
- Understand the data governance features of Experience Platform

## Lab Resources

- Experience Platform UI: [https://platform.adobe.com/](https://platform.adobe.com/)
- Sample data .parquet file in Profile XDM format: [ProfileDataSample.parquet](/data/ProfileDataSample.parquet)

## Lab Tasks

- Ingest and explore a .parquet file in the Experience Platform UI
- Understand data governance options in Experience Platform UI
- Ingest and confirm a .parquet file in the Experience Platform API

## Story Part 1: Using the UI

To start the base of the loyalty program, most companies are likely to have existing customer data. Here, we will perform a batch ingestion of an existing data file that contains customer profiles, pre-formatted in Profile XDM format. From the perspective of an Analyst/Architect ("Archie"), this will allow us to start adding customer data to Experience Platform through the web UI interface, as well as preview the ingested datasets to confirm using a snapshot of the data that the file and data has been correctly imported. Some data files may not be properly formatted in to Profile XDM format - in which case, a data ingestion may come up as `failed`. In addition, some fields in our Profile schema may be sensitive information - for example, a customer's address and phone number. These will need to be export-controlled using data governance.

For batch ingestion of data, it is important that the data is properly formatted into XDM prior to bringing it into our customer loyalty database on Experience Platform. Conversion of non-formatted data into Profile XDM will not be covered here, but will be assumed to have been performed prior by a Data Engineer ("Joe").

---

## Steps

### Using the Experience Platform Web UI:

1. Let's jump back to the [Web UI interface](https://platform.adobe.com), and click on the "Data" tab. This is where your ingested datasets will reside; once data has been ingested after this lab, it will look similar to this:

   ![](/images/chapter-4/ui-1-dataset_list.png)

1. We've got a list of datasets, but let's create our own. Click the "Create Dataset" button, and select the "Create Dataset" option under "Schema" after that.

   ![](/images/chapter-4/ui-2-dataset_creation.png)

1. Filter the datasets by typing "Profile" in the search box, and select the bottom-most "Profile" schema that pops up. Name your dataset as "[your name] Dataset"

   ![](/images/chapter-4/ui-2-dataset_creation2.png)

   ![](/images/chapter-4/ui-2-dataset_creation3.png)

1. Select "Browse" under "Add Data" on the right and navigate to the data file we've provided, ProfileDataSample.parquet.

   ![](/images/chapter-4/ui-2-dataset_creation4.png)

1. Wait a few moments, and then that status of the uploaded file should list as "Success".

   ![](/images/chapter-4/ui-2-dataset_creation5.png)

1. Let's take a look at it to make sure our data is in there. Click the "Preview" button to get a quick top-level view of a small sample of the dataset.

   ![](/images/chapter-4/ui-3-dataset_preview.png)

1. Alright, now that our customer loyalty data has been ingested, we want to make sure that this dataset is properly governed for usage and export control. Click on the "Data Governance" tabe and observe that we can set three types of restrictions: Contractual, Identity, and Sensitive Data.

   ![](/images/chapter-4/ui-5-data_governance.png)

1. Let's restrict identity data for the entire dataset. Hover over your dataset name, and click the Pencil icon to edit the settings. Go to "Identity Data" and check the "I2" option - this will assume that all pieces of information in this dataset are _at least_ indirectly identifiable to the person.

   ![](/images/chapter-4/ui-6-data_governance_flag.png)

1. Click "Save Changes" and observe that "I2" is now set for all data fields in the dataset. You can also set these flags for individual data fields - for example, the "person" field is likely an "I1" level for directly identifiable information.

   ![](/images/chapter-4/ui-7-data_governance_set.png)

1. Now that we've done these steps in the UI, we're going to move on to the API. Let's start fresh, so delete this dataset using the "Delete" button when you view the dataset, and move on to Part 2.

   ![](/images/chapter-4/ui-10-delete_dataset.png)

---

### Navigate

**Previous:** Chapter 3 - [UI: Define the Schema](/chapters/chapter-3.md)
**Next:** Chapter 5 - [UI: Segment the Data](/chapters/chapter-5.md)
