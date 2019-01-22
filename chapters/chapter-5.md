# 5. Segment the Data

## Learning Objectives

- Learn what the Unified Profile Service is and how to use it
- Learn how to segment an audience of Profiles

## Lab Resources

- Video Demo: **Demonstration of Segment Builder** by Aaron Shields, Senior Product Manager, Experience Cloud

## Lab Tasks

- Define a segment via API in JSON
- Create a segment job and export it to a new dataset
- Define a segment using the Segment Builder within Platform UI

---

## Story

Now that we have a system with customer basis profile data built on the Unified Profile Service and have demonstrated the ability to look up profile data, we can utilize Adobe Experience Platform to take further action. Using either the Segment Builder within the Platform UI or the Experience Platform APIs, Marketers ("Teresa") and Architects ("Archie") can specify filters to segment our database of customers. These segments can then be delivered directly to other platforms, including Adobe Campaign on Platform, where we can create actions built completely from our data that's stored on Experience Platform.

This will help with several aspects of our customer loyalty program, including targeted upgrade promotions, re-engagement or re-activation of customers, garnering insights from the loyalty program statistics, etc. Because all data for a customer including and beyond customer loyalty will be tied to one Unified Profile, we can bring in more information to segment, or use segments for a broader scope of actions.

---

## Steps

### Segmentation via the API

1.  Now that we've ingested some data in [Chapter 4](/chapters/chapter-4.md) into our Unified Profile service, we're ready to begin segmenting the data in order to gain insights.
1.  Start by expanding the `Chapter 5` & `Segmentation` folder in postman under `Adobe Experience Platform`.
1.  Select the `Profile: Create A Segment Definition` action. Note that in the body section of the action we are creating a simple segment that will include all males who have interacted with the system in the past 90 days.

    ![](/images/chapter-5/create_segment.png)

1.  Then click `Send` to create the segment and view the results in the response section of postman.

    ![](/images/chapter-5/create_segment_result.png)

1.  Now that we've been able to define a segment the next step is to start a job to run the segment query for us. So select `POST Segment Job` and hit `Send`.

    ![](/images/chapter-5/create_segment_job.png)

1.  A segment job may take a little while to run so let's check on it's status by selecting `GET Segment Job status` and hitting `Send`.

    ![](/images/chapter-5/create_segment_job_status.png)

    If the `status` property says `PROCESSING` wait a little longer and `Send` the query again until you see `SUCCEEDED`.

1.  Let's create a new dataset to hold the results of our segment job.

    ![](/images/chapter-5/create_segment_dataset.png)

1.  Now that the job has succeeded and we have a dataset to hold our segmentation data it's time to export the data. Select `POST Export Job` and hit `Send`.

    ![](/images/chapter-5/create_segment_export.png)

1.  We are getting close to being able to view our segment data. Select the `Get Export Job By Id` action and hit `Send`.

    ![](/images/chapter-5/create_segment_export_success.png)

    If the `status` property says `PROCESSING` wait a little longer and `Send` the query again until you see `SUCCEEDED`.

1.  Now the easiest way to view your segmented dataset is to log in to [https://platform.adobe.com](https://platform.adobe.com), click on the Data tab, then click on {{ldap}}\_ProfileSegmentDataset and finally the `Preview` button.

    ![](/images/chapter-5/create_segment_final.png)

    As you can see all of the people in the dataset are `male`.

---

### Segementation via the Segment Builder UI

Now that we've created a segment using JSON through the API, let's show how we can visually build one - helpful for those who may not want to write JSON, or simply want a web interface to do everything.

*NOTE: Unfortunately, current limitations on provisioning prohibits us from letting everyone access this feature. As such, we will do a live demo of the following steps, so follow along for your reference.*

1.  Head back to the main [Platform UI landing page](https://platform.adobe.com) and click on "Unified Profile", and then click the "Segmentation" tab. Here you'll see the "All Males" segement that we defined in the API already here.


    ![](/images/chapter-5/ui-1-segmentation_landing.png)

1. Click on "New Segment" and name it "All Females" in the "Edit Details" area.

   ![](/images/chapter-5/ui-2-new_segment.png)

1. First thing is to set our filter to define the segment. On the left side you'll see a list of fields based on the schema that make up the data in our Unified Profile database. Search for "gender" in the search box, and drag the first entry (Profile > Person > Gender) to the filter box on the right.

   ![](/images/chapter-5/ui-3-segment_picker.png)

1. You'll be promped to select a default value for this field filter based on its possible values. Select "equals" (already selected) and "Female". You'll see the estimate gauge at the top, showing 2750 profiles available, now estimates your filtered segment will contain about 1560 profiles.

   ![](/images/chapter-5/ui-4-segment_filter.png)

1. We can nest additional filters onto this segment to make it smaller. Let's say it's September, and we are running a birthday promotion for our female customers. Search for "birth month" in the filter search, and drag the "Profile > Person > Birth month" field under the Gender filter, to add it as an "And", and set it equal to 9.

   ![](/images/chapter-5/ui-5-segment_filter_and.png)

   You will see now that we have a specific segment of 118 profiles that we can target with this promotion! Since we're more specific now, edit the title of the segment to say "September-Born Females" instead.

1. Now that we've found our segment, hit "Create Segment". Now our segment will be saved to the Segmentation list alongside our API-created segment and can be used by other Platform-integrated solutions like Adobe Campaign! (In fact, Adobe Campaign on Experience Platform uses this Segment Builder UI directly inside its audience interface)

   ![](/images/chapter-5/ui-6-segment_created.png)

Great work! Now we've run through the basics of setting up your customer loyalty system based on Profile data - defining our data schema, ingesting data for that schema into Unified Profile, and segmenting our Unified Profile entries based on the segments you're targeting. What else can we do with this data now, and how else can we use or integrate into Adobe Experience Platform? We'll cover that next!

---

### Navigate

**Previous:** Chapter 4 - [Ingest the Schema](/chapters/chapter-4.md)
**Next:** Chapter 6 - [Integration and Connector Examples](/chapters/chapter-6.md)
