# 3. Define the Schema

## Learning Objectives

- Understand the structure of XDM Schema
- Learn to browse in view schema in UI
- Learn to list, lookup, create, and extend schema in API

## Lab Resources

- Experience Platform UI: [https://platform.adobe.com/](https://platform.adobe.com/)
- Profile XDM in JSON format: [ProfileXDM.json](/data/profileXDM.json)

## Lab Tasks

- List all the schemas
- Lookup the Profile schema
- Define a custom Profle schema for use with XDM
- Lookup the custom schema

## Story

Building a customer loyalty program requires a foundation. Here, we will define a "basis profile", which will be a standard Profile XDM schema that will serve as the basis for each customer's profile, and thus the Universal Profile that would be used across Experience Platform. The basis profile can be hydrated by ingesting existing profile data (for example, from an existing customer database) or through point-to-point connections from Adobe products such as Launch - we can see the frame for this profile in the Experience Platform UI in this step.

---

## Steps

### Using the Experience Platform Web UI:

1. We start with the Experience Platform landing page, which appears after navigating to [https://platform.adobe.com/](https://platform.adobe.com/) and logging in with your Adobe ID credentials.

	![](/images/chapter-3/ui-1-home.png)

1. From the this page, let's take a look at the many standard and custom XDM schema available to use by clicking the "Data Model" tab. Scroll through the list of available standard XDM data schema.

	![](/images/chapter-3/ui-2-schema.png)

1. Open "Profile" data schema and explore the visual structure of a standard XDM schema. Feel free to look at a few others as well.

	![](/images/chapter-3/ui-3-profile.png)

1. We can easily extend the core Profile XDM schema to fit our needs. For example, we can add a "loyaltyID" field to Profile by clicking the "+" button in the desired level. Try this out, and set the data type, but hit "CANCEL" when done so that we don't change this schema for now.

	![](/images/chapter-3/ui-4-addfield.png)

	![](/images/chapter-3/ui-4-addfield2.png)

1. We can also build schema from scratch - particularly if you have specific product data for your retail website, or reservation data for your hotel reservation system. From the "Data Models" tab, we can create a schema simply by clicking "Create Schema". Play with it here, but don't save your schema. The API steps after this will be your time to create.

	![](/images/chapter-3/ui-5-addschema.png)

	![](/images/chapter-3/ui-6-defineschema.png)


### API: Schema Querying and Creation

1. Now that you've successfuly been authenticated by following the steps in [Chapter 2](/chapters/chapter-2.md) you are now ready to make API calls.
1. Start by expanding the `Chapter 3` & `List Schemas` folder in postman under `Adobe Experience Platform`.
1. Select the `XDM: Get All Schemas` action and click `Send`.

   ![](/images/chapter-3/get_all_schemas.png)

   In the response pane you can scroll down and see all the schemas that are available in XDM.

1. There sure are a lot of schemas available in XDM but let's drill down a bit and view the `profile` schema. If you select `XDM: Get Profile Schema` and click `Send` you should see something similar to:

   ![](/images/chapter-3/get_profile_schema.png)

1. Now that we've seen the API calls to query schema let's move on to creating a custom schema of our own. Expand the `Create Schema` folder under `Chapter 3` in postman and select `XDM: Create New Schema` and click `Send`.

   ![](/images/chapter-3/create_schema.png)

   In the response section you will the path to your newly created schema which we will be using to create a dataset in `Chapter 4`.

1. Now select `XDM: Get Custom Profile Schema` and click `Send`.

   ![](/images/chapter-3/get_custom_profile_schema.png)

   The response section should return the details of the schema which look an awful lot like `Profile` schema. We've included a sample [ProfileXDM.json](/data/profileXDM.json) file in the repository if you'd like to compare them side by side.

With the creation of our custom schema we are ready to move on to the next step of creating datasets and data ingestion.

---

### Navigate

**Previous:** Chapter 2 - [Login and Accessing with Postman](/chapters/chapter-2.md)
**Next:** Chapter 4 - [Ingest the Data](/chapters/chapter-4.md)
