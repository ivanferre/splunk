# Splunk Core Certified User Udemy Course

## Basic Understanding of Splunk

Splunk is a software platform to search, analyze and visualize the machine-generated data gathered from the websites, applications, sensors, devices, etc which make up IT infrastructure and businesses.

## Splunk Architecture

Splunk's basic components are Indexer, Search Head and Forwarder. They are aimed to collect the data, store the data, and represent the data,

**Forwarders** take the inputs from various sources - syslogs, servers, any application, -  and sends them to the Indexer.

There are two types of Forwarder:

1. Universal Forwarder
    - Smallest footprint
    - Standard data collection
    - Unparsed / No Event breaking

2. Heavy Forwarder
    - Larger Footprint
    - Full Splunk Enterprise binary install
    - Allows filtering at source / in-flight

**Indexer** stores the data from forwarders  in flat files, generally based on time range. Indexes points to Events. It creates directories based on age.

The representation layer is in the **Search Head**. It is where user can get meaningful information from, and can present the information in many ways. It organizes data in fields, and may create objects to access to them.

There are other specialized components:

- Deployment Server
- Cluster Master¨
- License Master
