---
title: Test for client
deprecated: false
hidden: true
metadata:
  robots: index
---
WebEngage just got a new UI, that’s gonna amp up your experience with us. This document gives you a brief of all that you need to guide your way through your new dashboard.

> 🚧 Must Read
>
> Please ensure that you have a robust understanding of all the concepts related to _[Events and Event Attributes](events-and-event-attributes)_ before proceeding. Doing so will help you understand the working of this section better.

There are few changes and new additions to the features of the event analytics section. Let’s dive into each of the features in detail and where you’ll be finding them.

**First Impression**

The new UI of the events section consists of a blank dashboard, which will show you a graph as and when you select  the event/events that you'd like to analyze.

<Image align="center" alt={1440} caption="Click to enlarge" title="Events-overview.png" src="https://files.readme.io/9257628bdffa5ae3a218abe7c5f6064d4fe0053870e66b04392d570c66d23876-2nd.png" />

* On selecting the event from the drop down on the left you can analyze each of them in more detail
* Each event can be examined in greater detail by selecting their respective line or bar graphs or metrics.
* On doing so, you will be shown a day-wise breakup of total user activity.
* The results can further be refined by adding values to the fields of the drop down placed on top from where you can choose how you want to refine your data i.e. Hours, Days, Weeks, and Months.

<Callout icon="🆕" theme="default">
  ### This new UI introduces a smart search feature that goes beyond exact matches, delivering a range of relevant results based on your search query.
</Callout>

## Understanding features of the event analysis section

Now that you've got the hang of how this section works, let’s deep dive into its features to help you gain maximum insights:

### Step 1: Select the Date Range

<Image align="center" src="https://files.readme.io/de7e1dc9eb9c6ff0eaebadb2864c0c39bfe7c0f9c9dd10b2b25d30598fb38175-Screenshot_2024-10-09_at_10.17.50_AM.png" />

Using the date range filter placed on the top right, you can specify a period for which you want to analyze user behavior. The default period has been set to, _Last 7 days_.

### Step 2: Select Show (Occurrences, Uniques or Aggregate)

As discussed under, _[How are Events Calculated for Analysis?](events-and-event-attributes#how-events-are-calculated),_ there are three ways in which we calculate the number of times users perform an event; _occurrences_ and _uniques_ and _aggregate_.

As shown in the visual below, once you've selected the event or events you want to analyze, proceed to clicking on the dropdown below the selected event/s, that consists of the three option i.e. _Occurrences_ and _Uniques_ and _Aggregate_.

<Image align="center" alt={1438} caption="Click to enlarge" title="Events-Occurrences-Uniques-Options.png" src="https://files.readme.io/0138db3fc9fb8924ad9771906aab5b2bb737631b58667151a73efcdab82e47f3-Screenshot_2024-10-09_at_10.33.13_AM.png" />

Aggregation of data refers to summarizing or combining data to help users analyze trends beyond individual events. It is applied in dashboards for trend analysis (e.g., average spending over time) and respects event/ user filters.The process involves two levels:

* Level 1: Aggregating data at the user level (e.g., total spending by a user across multiple purchases).
* Level 2: Aggregating user-level data to show overall trends (e.g., average spending across all users).

**Types of Aggregation:**

* **Sum, Average, Median**: For numeric values (e.g., total/average spending).
* **Distinct**: Counts unique values (numeric or string).
* **Min/Max**: Finds smallest/largest values.
* **CountIfNull/ NotNull**: Counts null or non-null values.

**Note:** Handling Nulls/Blanks: Null/blank values are ignored in calculations, but actual zeros are valid data points.

### Step 3: Select the Event

Next, define the event you'd like to examine by choosing an event or a set of events from the dropdown nested under the field, _Events_ on the left.

<Image align="center" alt={1440} caption="Click to enlarge" title="Events-select-event.png" src="https://files.readme.io/a6e36648ffdc5cd794908e38969ba1377ea33a88a89c6eb0f51709025b0bb0d9-Screenshot_2024-10-09_at_10.40.49_AM.png" />

Follow the following steps to analyze the events of your choice

* Select the event that you want to analyze from the first option on the left column.
* Once you’ve selected an event, you are presented with a dropdown below the event you’ve selected to measure: **Occurrences** or **Unique** users.
* You can continue by adding more events by clicking on the ➕ Add Events in the events column.

<Image align="center" src="https://files.readme.io/e29127722a632e3d2e34cc6600a1d0ff050515ebce72191adc931510b108c890-new1.gif" />

_Multi Event_ allows you to gain a more in-depth understanding of how events may coincide or affect each other by plotting and comparing multiple events to visually spot any correlation between events.

<Image align="center" src="https://files.readme.io/f33041a695d70d070bad967320030931fddc1990a96f4a95752383f3664d2509-Screenshot_2024-10-22_at_3.15.46_PM.png" />

The drop-down includes all the system events, campaign events and custom events tracked for your account. All the system event and campaign events pre-defined by us are[ listed here](https://docs.webengage.com/docs/events) for reference.

> 🚧 Using Split by
>
> The Split by option will only be applicable while analyzing a _single event_. You can add up to **2 attributes** to be Split by (user + event)
>
> 2 level of split allows you to analyse cross cut of event data on 2 different attributes. In old UI, this was achieved using "Over" and "Split by" together.

#### Apply Attribute Filters to the Event

You can select individual filters for your events, through filtering them out on the event columns, under which dropdown you’ll be able to view ‘All Attributes (custom + system), or just Custom Attributes or only System Attributes.

<Image align="center" src="https://files.readme.io/3862acb482b20a3fcdd0a3bbcfbc44121e8a60a0825620b886f8e693561e4eee-ui.gif" />

Now let’s show you how to apply these attribute filters to the event, using the AND-OR logic.

<Image align="center" src="https://files.readme.io/228c893ec8854b3d17f2b8a5cfb09c0135598f629cd535494fcd8fbe8f0ea0a0-Screenshot_2024-10-22_at_3.22.58_PM.png" />

**Method 1: Using the AND logic to club attributes filters**

If we use the AND logic to apply all the attribute filters listed above, then your analysis will be limited to a set of users who have _only viewed Puma Running Pants, AND on the page, AND are from the US AND use an iOS device._

**Implications:** _So, using the AND logic to club event attributes you can narrow down the scope of analysis to a particular set of users whose actions fall in line with a sum of all the attributes._

**Method 2: Using the OR logic to club attributes filters**

If we use the OR logic to club and apply all the attribute filters listed above, then your analysis would include a broader set of users who have _either viewed Puma Running Pants OR have visited the page[www.companyname.com/women/pants](http://www.companyname.com/women/pants) OR have viewed any Product Page from the US OR have performed the event on an iOS device._

**Implications:** _So, using the OR logic to club event attributes you can broaden the scope of analysis by including users whose actions fall in line with any one of the attribute filters._

Hence, when using the OR logic, we suggest that you broaden the user base by clubbing related parameters together. For example, including the last two attributes; _Location_ and _OS_, doesn't help us gain any valuable insights as these parameters are unrelated to _Product Name_ and _Page URL_.

> 🚧 Note:
>
> It's not possible to add attribute filters when analysing _All System Events_ or _All Custom Events_ as the attributes which can be applied to each event, vary.

#### Step 3.2 : Select a Common Global Filter

You can also select a common filter for the events you’ve chosen above. These common filters have been categorized into 3 i.e. _User Attributes_,_Event Common Attributes_ and _Segments_.

<Image align="center" alt={1435} caption="Click to enlarge" title="Events-attribute-filter.png" src="https://files.readme.io/6af6a8868ba3cf5ce37179d65f002efee23bdd3e8c93712c251fbe42fdd184f5-new2.gif" />

##### User Attributes

This filter allows you to filter based on User Attributes:

* Once you’ve chosen the user attribute you want to use.
* You’ll be presented with an operator and criteria value you want to set for the respective attribute.

##### Event Common Attributes

This event filter allows you to choose from filters based on common event attributes:

* Once you’ve chosen the common event attribute you want to use,
* You’ll be presented with an operator and criteria value you want to set for the respective attribute.

##### List / Segments

Here you’ll be able to filter based on live segments/ lists (refreshing and static and predictive),

* You have the ability to include, exclude segments, or specify if you want users to be included/ excluded from all the listed segments or any of them.

### Step 4: Select the Dimension(s) for Analysis -Split By

The next step is to define the dimension(s) against which you'd like to analyze the event. The query bar has been designed to facilitate in-depth behavioral analysis by combining an exhaustive list of pre-defined parameters.

<Image align="center" src="https://files.readme.io/bbc2e992c43d618c889513b077bc91bc85e870c2c02bd3f6d845d55332025f0a-splitby.gif" />

Using the drop downs nested under the fields, _Split By_, you can combine up to two parameters to slice-and-dice your data.

<Callout icon="🆕" theme="default">
  ### _**The limit for the number of series displayed in the table has now been increased to 2000!**_

  For example, If you want to view a city ranked 2001 or lower, you'll need to apply a filter for that specific city within the Event filter
</Callout>

Currently, sorting occurs on the client side, meaning it is applied within the top 2000 series. This change will not only sort within the top 2000 series, but also allow you to retrieve the bottom 2000 series directly from your database.

> ❗️ Note
>
> When adding filters using attributes (User/Events), the right-handside (RHS) displays a dropdown with the first 200 values that entered the system as options for comparison. If the value you need is not listed, you can type it in manually.
>
> ####

#### Hours Granularity

Events can be analyzed on an hourly basis. To achieve this you can navigate to the ‘Over’ dropdown, where you can find ‘Hour’, by selecting this the graph that is produced will have hours on the X- axis. After which you can find the date and time (AM/PM format) on the X axis.  
This hour level granularity can be used with a period of 31 days i.e maximum of one month, if you try to increase the number of days beyond 31,  the ‘over’ option switches to the day option automatically along with an error.

**For last 7 days**

<Image align="center" src="https://files.readme.io/add8354a1dca1c40103950aaa31fa7b5daeae88c9196d6714eae4171f84705a1-Screenshot_2024-10-22_at_3.31.40_PM.png" />

**For Last 30 days**

<Image align="center" src="https://files.readme.io/dae27c4021abeb1e4e62e90ff4db6412dc4768b1abd68a6b32b8aecec836c565-Screenshot_2024-10-22_at_3.31.40_PM.png" />

### Step 5: Select the Format of Visualisation

Lastly, while _Bar Graph_ has been set as the default format of visualisation, you can change this to a _Line Graph_ or a _Table_, using the overflow menu placed on the top-right.

<Image align="center" alt={1439} caption="Click to enlarge" title="Events-visualization-format.png" src="https://files.readme.io/741263b0bd8e2f2f24a17f9bc122547cc176fabf7e8562cee6bdb6c5995318d7-Screenshot_2024-10-22_at_3.36.59_PM.png" />

#### Bar Graph 🆕

In the new EA approach, where the X-axis is always time, we will repurpose bar visualizations to better serve this need.

<Image align="center" src="https://files.readme.io/351e6d83b32f6846dabf559f33421de84f6aa3f9347d0f0d58b8cfd533a8de88-bar_graph.gif" />

Bar visualization will now display one horizontal bar for each series of a line chart, making data more accessible and actionable.

* **No Split**: Displays the aggregated event data over the selected time period.
* **With Split**: Shows aggregated event + user attribute (e.g., Session_Started by Country or Country-Browser) for deeper insights.

Bar values will reflect accurate aggregation for the time period, not just a simple sum of line chart data points, providing a more accurate representation of trends.

This new approach offers clearer insights with concise totals across the selected date range, while also resolving the challenge of visualizing data combinations like browser vs. country.

#### Metrics 🆕

You can now pin custom data points as cards to your dashboard directly from Event Analytics.

Selecting Metrics will display event counts, including the event name and any split (if applicable). For example, you’ll see something like “Product View [Occurrences] / Chrome,” with the count displayed below.

<Image align="center" src="https://files.readme.io/b658a6c311c535e8e6503e60e8e7dbb2d8a96c2569df515f7bb6467fff08fd28-metrics.gif" />

The Metrics option will only be available if you’ve selected 10 or fewer series. If more than 10 are selected, it will be disabled.

Metrics make it easier to track key data points at a glance, and you can tailor your dashboard to fit your needs.

## Actionable Event Analytics

Event analytics provides insights into your users behaviour, this becomes an important point where you can discover a segment of your users, for whom you would want to create a list for.

Additionally, you will be able to preserve an event analytics search or query as a list (Static and Refreshing Lists). This list may be for a single event or a collection of related events. Which can be further used to engage users by sending segmented campaigns.

### How it works?

Imagine you are doing analysis over a specific set of events and wish to create a list of users who did a particular event on a particular day. Now you will be able to export users list for a specific date or user list for over a period of time.s,

You can do this by clicking on the Zoom In option when you hover over the event you are analyzing.

<Image align="center" src="https://files.readme.io/26ab87de0f63a242f49edea1547e60a78b4b5233d5d0d5c4a1f90169baa4cacf-new3.gif" />

Lets understand 2 ways of creating List.

You can start by choosing between _Data Point or Series_:

For _**Data Points**_:

* The data point through which you selected the option to create a list, will be selected by default.
* The order will be the same as the way it is shown on the graph.
* You can also select all the data points.

<Image align="center" src="https://files.readme.io/f37c9e6fd58a0ab410d2a3c98095e9c3c7cc47d2f5afa56856cef4421a9b4fc9-new4-data_point.gif" />

For _**Series**_:

* The series through which you selected the option to create a list, will be selected by default.
* The order will be the same as the way it is shown on the graph except, for “Others”, they should be anchored at the bottom and should be unselected.
* You can also select all the series.

<Image align="center" src="https://files.readme.io/f90e03896a61f71e07f3fccb713f2f11ad2c35583f6a26824d0f2faaed75a2d1-new4-_series.gif" />

Let us consider a scenario where you choose to analyze the data points of an event. And walk through the steps of creating a list from event analytics.

* **Step 1:** You can now proceed with filling up the name of the list you want to create.

<Image align="center" src="https://files.readme.io/194e6f434150c2742f6ff68d1de397e2bf0c6a6b047ca5cd7c39c70e1783c2d5-new4-_list.gif" />

* **Step 2:** Now choose from the type of list i.e. _Static or Refreshing_.
  * **Static:** A one time list, where users will not receive them again and are used for executing campaigns for a small group of users, these are ideal for running one-off campaigns where your end goal is to invoke immediate action like user activation, conversion, registration, or convey a personalized message. Click [here](https://knowledgebase.webengage.com/docs/static-segments) to know more.
  * **Refreshing:** refers to a type of list that you can update or reload either by manually triggering a refresh action or by setting a periodic schedule i.e. daily, weekly, monthly, for automatic refreshing. Click [here](https://knowledgebase.webengage.com/docs/refreshing-lists) to know more.

<Image align="center" src="https://files.readme.io/76d452fe0990057af13f30fcd15bbe4b83eae4459df5cb90fa5b797a445b0c03-Screenshot_2024-10-22_at_3.45.55_PM.png" />

> 📘 Keep a note
>
> Refreshing list cannot be created with existing refreshing list as filters.

* **Step 3**: If you’ve chosen the Refreshing lists option, Last ‘x’ days.
  * For **Refreshing Type**, text will be displayed with the last X days and number of days are editable in the future.

<Image align="center" src="https://files.readme.io/5d091a1b20e92e4e6987ba6cfe154bf572647cc71312e42d114eb08bfd9b6079-Screenshot_2024-10-22_at_3.48.14_PM.png" />

* **Step 4: Selecting Refreshing Frequency:** : A refresh schedule, similar to the one we have for the refreshing segment, to refresh the lists in every time period such as daily, weekly, or monthly.

Once the above fields have been filled, you can now proceed to selecting the data points or series from the table below.

<Image align="center" src="https://files.readme.io/3c926896bf5831d6d8834c53d879b09b4764fe0d57867791f521c3d928b9fe52-new5.gif" />

> 👍 Use Case
>
> **User Onboarding Optimization**:
>
> _Brief_: Track user onboarding touchpoints, including account creation, profile completion, tutorial views, and feature interactions. Access a comprehensive view of the onboarding process, enabling a nuanced understanding of user interactions.  
> _Impact_: Granular insights allow for targeted improvements to the onboarding journey, resulting in a smoother user experience.
>
> **Product Feature Adoption:**
>
> _Brief:_ To track the adoption of specific product features, combine multi-event analytics with segment and static list filters. By analyzing events related to feature usage and creating segments based on user behavior, tailor communications sent to different user groups. User attributes can further refine this targeting.  
> _Impact:_ A personalized approach to promoting features, increasing user engagement, and driving feature adoption.
>
> **User Engagement Journey Mapping**
>
> _Brief:_ Identify key touch points, behaviors, and preferences in the user journey; user attributes further refine insights. Export this data to allow for a comprehensive understanding of the user journey.  
> _Impact:_ Informed decision-making, personalized marketing strategies, and an improved overall user experience.

**Step 5:** Click on Create List to save the list  
Once the lists have been saved, they will be visible to you under the Segment section under Lists.

<Image align="center" src="https://files.readme.io/95974cf53f64e3eab55d83019b19c2ce2adf46529b5a96c550ce5f59b5a8f381-Screenshot_2024-10-22_at_3.52.34_PM.png" />

> 📘 Keep in mind
>
> Once the list is created and saved you cannot update the criteria of the list. You can follow the same steps in case you want to analyze Events for Series List.

We hope this has given you a good idea of how you can make the most of the _Events_ section of your dashboard to gain relevant behavioral insights. Please feel free to reach out via _[support@webengage.com](mailto:support@webengage.com)_ in case you have any further queries. We’re always happy to help!
