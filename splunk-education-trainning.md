# Splunk Education Trainning

## Intro to Splunk

Limiting the time scope is the most efficient way to optimize searches.

Default search fields: index, source, host, sourcetype.
They are the most powerful. They are extracted at 'index time'(?), so they won't need to be extracted for each search.

## Splunk Knowledge

Source: [Knowledge Manager Manual](https://docs.splunk.com/Documentation/Splunk/8.0.4/Knowledge/WhatisSplunkknowledge)

Splunk software extracts different kinds of knowledge from your IT data (events, fields, timestamps, and so on) to help you harness that information in a better, smarter, more focused way. Some of this information is extracted at index time, as Splunk software indexes your IT data. But the bulk of this information is created at "search time," both by Splunk software and its users. Unlike databases or schema-based analytical tools that decide what information to pull out or analyze beforehand, Splunk software enables you to dynamically extract knowledge from raw data as you need it.

Splunk software knowledge is grouped into five categories:

**Data interpretation**
: Fields and field extractions - Fields and field extractions make up the first order of Splunk software knowledge. The fields that Splunk software automatically extracts from your IT data help bring meaning to your raw data, clarifying what can at first glance seem incomprehensible. The fields that you extract manually expand and improve upon this layer of meaning.

**Data classification**
: Event types and transactions - You use event types and transactions to group together interesting sets of similar events. Event types group together sets of events discovered through searches, while transactions are collections of conceptually-related events that span time.

**Data enrichment**
: Lookups and workflow actions - Lookups and workflow actions are categories of knowledge objects that extend the usefulness of your data in various ways. Field lookups enable you to add fields to your data from external data sources such as static tables (CSV files) or Python-based commands. Workflow actions enable interactions between fields in your data and other applications or web resources, such as a WHOIS lookup on a field containing an IP address.

**Data normalization**
: Tags and aliases - Tags and aliases are used to manage and normalize sets of field information. You can use tags and aliases to group sets of related field values together, and to give extracted fields tags that reflect different aspects of their identity. For example, you can group events from set of hosts in a particular location (such as a building or city) together--just give each host the same tag. Or maybe you have two different sources using different field names to refer to same data--you can normalize your data by using aliases (by aliasing clientip to ipaddress, for example).

**Data models**
: Data models are representations of one or more datasets, and they drive the Pivot tool, enabling Pivot users to quickly generate useful tables, complex visualizations, and robust reports without needing to interact with the Splunk software search language. Data models are designed by knowledge managers who fully understand the format and semantics of their indexed data. A typical data model makes use of other knowledge object types discussed in this manual, including lookups, transactions, search-time field extractions, and calculated fields.

Also, be aware that when searches and pivots are slow to complete, you may use Summary-Based reports and Data Model Acceleration to speed things up.

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

Splunk Knowledge objects can be managed through **configuration files**.

The **Pivot tool** helps users to create reports and dashboards without having to develop large and complex search expressions. The Pivot tool requires the definition of **data models** to do so.

Large volumes of data can result in slow performance for Splunk software, whether you're launching a search, running a report, or trying to use Pivot. To speed things up the knowledge manager can make use of report acceleration, data model acceleration, and summary indexing to help ensure that the teams in your deployment can get results quickly and efficiently.

#### Technical Add-Ons

When you have a known data type coming in, you can implement a technical add-on. This add-on will take the data, ingest it, and apply known rules to it.

The technical add-ons use event data and group the data sets by common terms instead of the vendor term. How is this helpful? The ability to search by common terms allows for easier communication flow across teams. Common terminology, via the Common Information Model (CIM), helps with communication across vendors and teams.

## Fields
