# Adobe Experience Platform SPP Workshop

- Date: January 29th-30th, 2019
- Participants: Adobe Partners
- Instructors: Klaasjan Tukker (ktukker@adobe.com), Simon Mac Donald (smacdona@adobe.com), Ryan Dumlao (dumlao@adobe.com), Sarah Xu (saxu@adobe.com)

### Overview

This workshop is intended to cover the following topics in both UI and API settings:

- Adobe Experience Platform overview and use cases
- Getting set up on and using Adobe Experience Platform
- XDM (Experience Data Model) data schema
- Data ingestion (APIs and UI)
- Data lookup, processing, and querying
- Dataset visualization in Experience Platform UI
- Unified Profile, Segment Builder
- Adobe Launch and streaming data in to Platform

### Schedule

| Day 1 (1/29) | Time Block        | Scheduled Event                                                        |
| ------------ | ----------------- | ---------------------------------------------------------------------- |
|              | 4:00 PM - 5:00 PM | Technical setup and preparation (provisioning, access, software tools) |

| Day 2 (1/30) | Time Block          | Scheduled Event                            |
| ------------ | ------------------- | ------------------------------------------ |
|              | 10:00 AM - 10:15 AM | Tech Keynote - Jim Rivera                  |
|              | 10:15 AM - 12:30 PM | Morning hands-on lab, Part One             |
|              | 12:30 PM - 1:30 PM  | Networking Lunch & Break                   |
|              | 1:30 PM - 5:00 PM   | Afternoon hands-on technical lab, Part Two |

### Story

A company running a business in Retail or Hospitality can use Adobe Experience Cloud products for a variety of reasons. One of those use cases applicable to these verticals is that of a customer loyalty program. This would include creating a "basis profile" for a specific company's customer, using identifiable information including full name, contact information, and other details. This profile would then serve as a base point to tie additional unique data including transaction history, loyalty program eligibility and status, as well as behavioral data such as online browsing habits to drive promotions and other actions.

Having this "basis profile" established in the Adobe Experience Platform, using a Unified Profile, will give the company the ability to tie multiple sources of data from Experience Cloud products as well as external products built with connections into the Adobe Experience Platform. This will help the company understand a full 360-degree view of each of their customers, as well as perform useful actions such as segmenting customers, querying the data, and defining live data to include.

This workshop covers a portion of this story, that of establishing a basis profile for a company's customers, either through batch ingestion or connector ingestion, in order to begin the foundation for a customer loyalty program built on Adobe Experience Platform. It will then cover building in live data streaming from a website into Experience Platform via Launch.

### Scope

We will cover using the Experience Platform UI to perform XDM data ingestion and segmentation. The 2nd part oft he workshop will cover the same use-cases using the API, as well as using the Profile Query Service to query existing data, and setting up streaming data of behavioral and profile data from a website using Adobe Launch.

### Goals

After completion of this workshop. you should be able to:

- Define and select an XDM Schema
- Ingest sample data in XDM format into Adobe Experience Platform
- Segment profiles created in the Unified Profile Service based off ingested data
- Understand what can be done with XDM data and Unified Profiles
- Query the data ingested into Experience Platform using Profile Query Service
- Set up a Launch streaming endpoint and build rules to stream data from a webpage into Platform

#### Workshop Info & Credentials

These will be supplied to you with a handout and are unique to each registered participant.

#### Resources to download

- [Experience Platform API Postman Collection](postman/PlatformSupport.postman_collection.json)
- [Experience Platform API Postman Environment](postman/PlatformSupport.postman_environment.json)
- Sample Profile XDM Data
  - [ProfileData.parquet](data/ProfileDataSample.parquet)
- [WeTravel Website](data/WeTravel-local.zip)
- [Link to Adobe Experience Platform sign-in page](https://platform.adobe.com)

#### Chapters

##### Setup

- Chapter 1 - [Before you start: Pre-Authorization and Tools](chapters/chapter-1.md)
- Chapter 2 - [XDM and Experience Platform Overview](chapters/chapter-2.md)

##### UI-Based Lab

- Chapter 3 - [Schema: Explore and Define XDM Schema](chapters/chapter-3.md)
- Chapter 4 - [Data: Ingesting Data via Batch Ingestion](chapters/chapter-4.md)
- Chapter 5 - [Segmentation: Building Segments from Unified Profiles](chapters/chapter-5.md)

##### API and Technical Lab

- Precursor - [Login and Accessing with Postman](chapters/chapter-6-precursor.md)
- Chapter 6 - [Schema: Explore and Define XDM Schema](chapters/chapter-6.md)
- Chapter 7 - [Data: Ingesting Data via Batch Ingestion](chapters/chapter-7.md)
- Chapter 8 - [Querying: Using the Profile Query Service](chapters/chapter-8.md)
- Chapter 9 - [Streaming: Stream in Data using Launch](chapters/chapter-9.md)

##### Bonus API Content

- Chapter 10 - [Segmentation: Segment the Data using the API](chapters/chapter-10.md)

#### Administrative (remove before Summit)

[Checklist for changes to 2018 Workbook by 1/30](new-layout.md)
