# Splunk Education Trainning

## Intro to Splunk

Limiting the time scope is the most efficient way to optimize searches.

Default search fields: index, source, host, sourcetype.
They are the most powerful. They are extracted at 'index time'(?), so they won't need to be extracted for each search.

## Splunk Knowledge

Splunk software extracts different kinds of knowledge from your IT data (events, fields, timestamps, and so on) to help you harness that information in a better, smarter, more focused way. Some of this information is extracted at index time, as Splunk software indexes your IT data. But the bulk of this information is created at "search time," both by Splunk software and its users. Unlike databases or schema-based analytical tools that decide what information to pull out or analyze beforehand, Splunk software enables you to dynamically extract knowledge from raw data as you need it.

### Splunk Knowledge Objects

Article: [Splunk Knowledge Objects: What They Are & How to Use Them](Splunk Knowledge Objects: What They Are & How to Use Them)

**Index**
: A collection of data that is searchable and that can be retrieved using Splunk’s search language. Data is stored in indexes according to a set of rules and configurations.

**Source types**
: Labels that help Splunk determine the format of incoming data. Source types determine how data should be parsed and interpreted, allowing Splunk to extract fields and transform the data.

**Fields**
: Key-value pairs that contain specific data values extracted from events. Fields can be created automatically or defined manually by users. To create a field manually, you can use the Fields menu to create a new field and define its attributes.

**Search-time field extractions**
: configurations that allow users to create new fields based on the content of existing fields. They can be defined through configuration files.

**Lookups**
: Tables of data used to add context to events or map fields to different values. They’re typically created from CSV files or databases and can be used in searches and visualizations.

**Event types**
: Named collections of events that share similar characteristics or properties. Their purpose is to simplify searches, provide a higher level of abstraction, and help with reporting and alerting.

**Alerts**
: Configurations that trigger an action when a specific condition is met, specifically: sending notifications or running scripts.

**Reports**
: Saved searches that are scheduled to run at specific intervals and generate visualizations or summaries of data.

**Dashboards**
: Customizable displays that show real-time or historical data in the form of charts, tables, or other visualizations.

**Tags**
: Labels that can be applied to events, fields, or sources to categorize and group them. Tags can be created manually or defined through search-time extractions.

An example would be to trace a _transaction-id_. If we tag it at the firewall event, we may trace it later at the webserver and database events as well.

    tag::host="WebserverName"

Tags can help to centralize the naming conventions behind your data and knowledge objects.

#### Technical Add-Ons

When you have a known data type coming in, you can implement a technical add-on. This add-on will take the data, ingest it, and apply known rules to it.

The technical add-ons use event data and group the data sets by common terms instead of the vendor term. How is this helpful? The ability to search by common terms allows for easier communication flow across teams. Common terminology, via the Common Information Model (CIM), helps with communication across vendors and teams.

## Fields
