# llSPS-INT-214-AI-Powered-News-Search-App-Level-1-
AI Powered News Search App (Level-1)

# Query Watson Discovery News using the Watson Discovery Service

## Summary

The web is home to massive amounts of data, with more being created every day. Organizations can harness this constant stream of information to gain understanding, plan strategies, and find opportunities. Enriched news data can help your application make dynamic connections across current events faster. In this exercise, you'll start with the basics and build your own news mining web application using JavaScript, Node.js, and the Watson Discovery service. In this exercise:

* Code is written in Node.js
* You'll use the pre-built Watson Discovery News collection
* You'll access the Watson Discovery service through the Watson Discovery API

Optionally, you can choose to:

* Use a Slack interface to query the data
* Push news alerts out to an RSS reader
* Host the app on the IBM Cloud

## Description

This code pattern shows you how to tap into massive data sets to mine insight. You'll build a news mining web application with the Watson Discovery service using the Watson Node.js SDK. The app demonstrates two use cases using Watson Discovery News:

* **Search**: Query for the most relevant new articles about a specific topic or subject. Because the news collection is pre-enriched with natural language processing, you can query not just on keywords or categories but also on concepts, sentiment, and relations to get richer search responses.

* **Trending topics in the news**: Identify popular topics over the past 24 hours. Topics can be general, or specific to an industry or category.

## Flow

![architecture](doc/source/images/architecture.png)

1. The user interacts with the Watson Discovery News Server via the app UI.
1. User input is processed and routed to the Watson Discovery News Server.
1. The Watson Discovery News Server sends user requests to the Watson Discovery Service.
1. The Watson Discovery Service queries the Watson News Collection.
1. The Watson Discovery Service responds to Slack search requests.

# Included components

* [Watson Discovery](https://www.ibm.com/watson/services/discovery/): A cognitive search and content analytics engine for applications to identify patterns, trends, and actionable insights.

# Featured technologies

* [Node.js](https://nodejs.org/en/): An asynchronous event driven JavaScript runtime, designed to build scalable applications
* [Slack](https://slack.com): Slack is a cloud-based set of team collaboration tools and services with chat bot integration
* [Botkit](https://www.botkit.ai): Framework for creating and managing chat bots

## Sample output

The trending page:

![demo](doc/source/images/sample-output-trending.png)

<br>

The query page:

![demo](doc/source/images/sample-output-query.png)

<br>

* Part 1 - Navigating the UI
* Part 2 - Code walkthrough
* Part 3 - Watson Discovery service APIs

[![](https://img.youtube.com/vi/QFwbrTkigmI/0.jpg)](https://www.youtube.com/playlist?list=PLOCckZJT4e3OzgykV0mEpZE6zKHysgIr6)

# Extra Credit

Now that you have built the base application, here are some additional steps you can take to add a Slack interface, and/or provide a way to send new trending news topics to your favorite RSS feed.

## 1. Configure Slack

To integrate a new Slack Bot into your existing Slack team, navigate to `https://<my.slack.com>/apps/manage/custom-integrations`, where `<my.slack.com>` is the Slack workspace you want to customize.

  1. From the **Cutsom Integrations** page, select the **Bots** option.

![slack-integrations](doc/source/images/slack-0.png)

  2, To add a new bot, select the **Add Configuration** button.

![slack-integrations](doc/source/images/slack-00.png)

  3. Enter a username for the bot and click **Add bot integration**.

![slack-bot-name](doc/source/images/slack-1.png)

  4. Once created, save the **API Token** that is generated.

![more-slack-config](doc/source/images/slack-2.png)

## 2. Configure the application to use the Slack bot

### If you runnint the app locally...

  1. Edit the .env file and enter the Slack Bot **API Token** saved in the previous step.

```bash
# Slack
SLACK_BOT_TOKEN=<slack_bot_token>
```

  2. Restart the application.

## Search from Slack

The slack bot will respond to certain key words, below is a sample dialog. Remember to `@` the bot each time, or start a private chat. Make sure to invite your bot into other channels using `/invite @<my bot>`.

```bash
user: @newsbot hi
newsbot: Hello.

user: @newsbot news please
newsbot: Hi there! What news are you interested in?

user: @newsbot toronto raptors
newsbot: You want me to search for news articles about `toronto raptors`?

user: @newsbot yes
newsbot: OK searching...
```

![slack](doc/source/images/slack-3.png)

# Links

* [Demo on Youtube](https://youtu.be/EZGgvci9nC0): Watch the video.
* [Watson Node.js SDK](https://github.com/watson-developer-cloud/node-sdk): Download the Watson Node SDK.
* [Cognitive discovery architecture](https://www.ibm.com/cloud/garage/architectures/cognitiveDiscoveryDomain): Learn how this code pattern fits into the Cognitive discovery Reference Architecture.
* [Overview of the Watson Discovery service](https://www.ibm.com/watson/services/discovery/): Extract value from unstructured data by converting, normalizing, enriching it.
* [Three ways IBM has evolved Alchemy Data News into Watson Discovery News and made it even better](https://www.ibm.com/blogs/watson/2017/04/3-ways-ibm-evolved-alchemy-data-news-watson-discovery-news-made-even-better/): Watson Discovery News takes big steps forward in NLP-enriched news search.
* [IBM launches Watson Discovery Service for big data analytics at scale](https://www.techrepublic.com/article/ibm-launches-watson-discovery-service-for-big-data-analytics-at-scale/):
Suite of APIs makes it easier for companies to ingest and analyze their data, even if they don’t have advanced degrees in data science.
* [SlideShare: Building with Watson – Network Visualizations using Watson Discovery](https://www.slideshare.net/IBMWatson/building-with-watson-network-visualizations-using-watson-discovery): See an app built on the Watson Discovery Service and D3.js that helps you explore your data using a network map built on NLP metadata.

