# Chapter 3. Schema: Explore and Define XDM Schema

## Learning Objectives

- Learn what the Unified Profile Service is and how to use it
- Learn how to segment an audience of Profiles

## Lab Resources

- Video Demo: **Demonstration of Segment Builder** by Aaron Shields, Senior Product Manager, Experience Cloud

## Lab Tasks

- Define a segment via API in JSON
- Create a segment job and export it to a new dataset
- Define a segment using the Segment Builder within Platform UI

## Story

Building a customer loyalty program requires a foundation. Here, we will define a "basis profile", which will be a standard Profile XDM schema that will serve as the basis for each customer's profile, and thus the Universal Profile that will be used across Experience Platform. The basis profile can be hydrated by ingesting existing profile data (for example, from an existing customer database formatted in XDM) or through point-to-point connections from Adobe products such as Launch (covered in Chapter 9) - we can see the frame for this profile in the Experience Platform UI in this step.

---

## Steps

### Using the Experience Platform Web UI:

#### Browse and view existing schema

1. We start with the Experience Platform landing page, which appears after navigating to [https://platform.adobe.com/](https://platform.adobe.com/) and logging in with your Adobe ID credentials.

	![](../images/chapter-3/ui-1-home.png)

1. From the this page, let's take a look at the many standard and custom XDM schema available to use by clicking the "Data Model" tab. Scroll through the list of available standard XDM data schema.

	![](../images/chapter-3/ui-2-schema.png)

1. Open "Profile" data schema and explore the visual structure of a standard XDM schema. Feel free to look at a few others as well.

	![](../images/chapter-3/ui-3-profile.png)

#### Extending and creating schema

1. We can easily extend the core Profile XDM schema to fit our needs. For example, we can add a "loyaltyID" field to Profile by clicking the "+" button in the desired level. Try this out, and set the data type, but hit "CANCEL" when done so that we don't change this schema for now.

	![](../images/chapter-3/ui-4-addfield.png)

	![](../images/chapter-3/ui-4-addfield2.png)

1. We can also build schema from scratch - particularly if you have specific product data for your retail website, or reservation data for your hotel reservation system. From the "Data Models" tab, we can create a schema simply by clicking "Create Schema". Play with it here, but don't save your schema. The API walkthrough will be your time to create a custom schema.

	![](../images/chapter-3/ui-5-addschema.png)

	![](../images/chapter-3/ui-6-defineschema.png)


---

### Navigate

**Previous:** Chapter 2 - [Setup: XDM and Experience Platform Overview](chapter-2.md)

**Next:** Chapter 4 - [UI: Data: Ingesting Data via Batch Ingestion](chapter-4.md)

**Return Home:** [Workbook Index](../README.md)