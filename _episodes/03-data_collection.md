---
title: "Data collection screen"
teaching: 20
exercises: 10
questions:
- "How do we collect data from Twitter?"
- "How can we specify criteria for a data collection?"
objectives:
- "Understanding the data collection process. "
keypoints:
- "COSMOS can collect twitter data from Twitter."
- "COSMOS can filter collection based on a variety of criteria."
- "COSMOS can create many subset data while the collection continues."
---

## Before We Start
- Setup COSMOS.
- Authorising your Twitter account to collect data.
- Check if there is any update.

# Lessons
***
## 1) Collection Process

Twitter API allows COSMOS to stream public Tweets from the platform in real-time. COSMOS uses filtered stream endpoints to narrow criteria you defined from the COSMOS interface such as `keywords`, `hashtags`, `account names`, `language`, `place`(See in the *Data Collection Screen* section). Creating a filter is helpful because it prevents you from collecting unwanted tweets for your research.

After you start a collection through COSMOS, you will begin receiving a stream of data. All streamig data is saved in JSON format with `/home/COSMOS-files/tmp` path temporarily. For each collection, COSMOS creates a folder which has the same name with the collection in the `tmp` folder. Folder structure:

`<%collection_year%>/<%collection_month%>/<%collection_day%>/twitter-collection-<%hour%>.json` 
![Folder Structure](../fig/Folder-structure.png){:height="300px" width="600px"}

Since COSMOS does not show all entities from the raw streamed data, the temp files would be beneficial to access these. Later, COSMOS creates a Mongo DB (local database on your machine) and moves the dataset to the database from *'tmp'* folder.

## 2) Data Collection Screen
After setting up COSMOS on your machine, you can start the software as it is instructed. 

Once COSMOS is launched in your browser, click the plus button on the top left corner. There are options `Import Data`, `Import RSS Feed` and `Start Twitter Collection`. You will start a Twitter collection:

1. Click `Start Twitter Collection`.
2. Give an appropriate name for the collection on the `Twitter Collector` pop-up window.
![Twitter collector](../fig/Twitter_Collector.png){:height="500px" width="500px"}
3. Start the collection based on filtering criteria: `Keywords and hashtags`, `Language`, `Location`, `Twitter accounts` and `Maximum number of tweets` by filling the form. 
4. When the form is filled, click the submit button. Once the collection starts, it appears on the show panel.
![Collection start](../fig/collection-start.png){:height="250px" width="500px"}

> ## 3) More on Collections
>
> The collection takes time as it streams tweets in real-time.    
> **While the collection continues**, clicking the three dots on the show panel:
> * Stop the collection when enough data has been collected.
> * **Snapshot** the collection to create a subset data which has been collected until the snapshot.
> ![Snapshot](../fig/take-snapshot.png){:height="250px" width="400px"}
> 
> **When the collection has been stopped**, clicking the three dots on the show panel: 
![Collection menu](../fig/collection_menu.png){:height="250px" width="350px"}
> * **Query:** You can filter your collected data based on `tweets sentiment`, `date`, `gender`, `language` and `country`.
![Query](../fig/Query.png){:height="300px" width="400px"}
> When you query the dataset, it creates another subset data based on the query details. This feature helps to remove noisy data and shorten data analysis process. 
> * **Export Data Details**
> * **Export collected data:** Exports collected data as a csv file.
> * **Delete**
> * **Details of data set:** Exports dataset's details as a json file such as started date, name of the collection,...
>
>
>
{: .callout}

  
***  
#### You can also watch youtube video clicking the image below for all data collection process with COSMOS.
***

<iframe width="560" height="315" src="https://www.youtube.com/embed/FfkSW46scLM" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

> ## Exercise
> Collect `10000` english tweets using ``, `` keywords, for ``, `` Twitter accounts using COSMOS 2.0
>
{: .challenge}

> ## Exercise
> While collection continues; 
> 1. Create a subset and give it an appropriate name. 
> Which COSMOS feature did you use for this purpose? 
> 2. Create and name a subset filtering only sentimentally
> `negative` tweets in the `last two days`.
> Which COSMOS feature did you use for this purpose? 
>
> > ## Solution
> > 1. Click 3 dots on the panel and select `Snapshot`. After creating a subset click 3 dots and choose `Details` option from dropdown menu, edit the name of the subset and hit the `Update` button.
> > ![Snapshot](../fig/name-snapshot.png){:height="200px" width="400px"}
> > 2.  Click 3 dots on the panel and select `Query`. Then, fill the form on the pop-up window choosing sentiment score as a negative number(between -5 to 0) and entering date of last two days and click the `Query` button. After creating a subset, click 3 dots again and choose `Details` option from dropdown menu, edit the name of the subset and hit the `Update` button.
> {: .solution}
{: .challenge}

