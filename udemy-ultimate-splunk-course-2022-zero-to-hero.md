# Ultimate Splunk Course 2022 From Zero to Hero

## Introduction

Splunk is a centralized tool for collecting and analyzing logs.

It provides search capabilities to summarize, standarize, filter, and analyze large and diverse amounts of log files.

Further, it can turn events (log entries) into reports and dashboards.

## Important Ports

Default values:

- 8000: Webserver Port
- 9997: Receiving Port (data from the forwarders)
- 8089: Forwarding Management Port (check the statuses of the forwarders)

### Deployment Types

### Simple deployment

We only have one single search head that's able to view all the logs coming in and we tipically have less than 100 users.

We just have around a couple of orders, a few indexers, collecting the data that's being sent by the forwarders.

[img1]

### Head cluster deployment

We have the second deployment, which is a search.

If you have two or more different types of components, that is considered a cluster.

This is a good idea to avoid having a single point of failure, and to be able to load balance all of the information that is coming in.

So at the top we need the load balancer. Therefore, all the information that is going to be viewed by the user level, it will hit the load balancer, and then the load balancer will distribute out evenly the number of resources that each of these search heads to have in order to process all the data.

### Index cluster deployment

It's similar to the search head cluster deployment where you have redundancy and all the information is being basically offloaded to each index, and each index will have a copy of all the logs.

So if one index were to go down, the other two indexes will basically have copies of the data and this will get put over into one search head.

There is a fourth method which is basically combining the cluster index deployment and the cluster search and deployment, and that's just basically having a combination of clusters with those two types of things.
