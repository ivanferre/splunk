# Splunk

## Teaching Assistant

Dominic Järmann
E-Mail: <dominic.jaermann@icloud.com>
Telephone: 0787367787

## Welcome

Good morning everyone, I hope you are doing well after this sunny weekend! I'm Dominic and I am a Penetrationtester and also responsible for IT Security in a small-ish startup.

I heard you want to learn how to use splunk. Great! In my opinion you learn it best in a hands on execise with the BOTSv3 Dataset. BOTS = Boss of the SOC (Security Operations Center).

I have setup a BOTSv3 envrioment here: <http://3.67.98.121:8000/> user: powercoders, passwort: $H0l1d41s$.

To get a initial overview of splunk, please watch the following video: <https://www.youtube.com/watch?v=GWl-TuAAF-k&list=PL7zWAA-DF0k_sxswRiB7_GUTyI0FoV7lc&index=2>.

I will give you the questions in a shortwhile (once I found out how to feasibly export an csv file to a pdf :slightly_smiling_face:). Anyhow I believe this course is entirely possible in a self learning envrioment.

Use youtube and google to your advantace. There are also many solutions for the questions out there so you can find out how exactly it has been solved. One of which is this: <https://ellisstannard.medium.com/boss-of-the-socs-bots-v3-part-1-3a0d92b851b4>. But try to solve it yourself first and if you cannot find a solution only then look it up online.

Also find attached a Quick Reference Handbook for splunk. When I first learned splunk this Pdf was my best friend.

On a sidenote: If someone of you wants to go into the field of Penetration Testing and wants to do some work related to this instead of splunk (which is only SOC) please reach out to me. :slightly_smiling_face: Happy Logging.

## Splunk SIEM Basics For Beginners

[Splunk SIEM Basics For Beginners | TryHackMe Splunk: Basics](https://www.youtube.com/watch?v=Wd0uHZL1L1U)

Splunk is a **SIEM tool**: Security Information and Event Management.

- Collecting **logs** from hosts and network devices,
- Normalizing,
- Analyzing, and
- Alerting.

All depends on the configuration of the **rules**.

Splunk consists of 3 components:

- Forwarder: the agent tool which you install on hosts and devices, and collects all the logs.
- Indexer: processes the logs collected by the forwarder, and stores them.
- Search head: enables searching into the normalized logs.

When you want to install Splunk, you first install the forwarder agents.

Indexes normalizes and stores the data in _field=value_ pairs.

### Acquire Data

Three ways:

- Upload data from local computer.
- Forward data from a Splunk agent installed on an end-point or network device.
- Monitor files or ports on a Splunk instance.

## Splunk CIM

[Demystifying the Splunk CIM](https://youtu.be/BR2uPHTAFSo)

Common Information Model (CIM) provides methodology for normalizing values to a common field name. Uses a common schema to search data,, running reports, and create dashboards.

Splunk offers JSON data model files to help validate indexed data for compliance, use normalized data in pivots, and improve performance through data model  acceleration.

Free add-on at: [splunkbase.splunk.com](splunkbase.splunk.com)

## TODO

Video: <https://www.youtube.com/watch?v=GWl-TuAAF-k&list=PL7zWAA-DF0k_sxswRiB7_GUTyI0FoV7lc&index=2>

 BOTSv3 envrioment: <http://3.67.98.121:8000/>

 [Splunk Boss of the SOCs (BOTS) V3 — Part 1](https://ellisstannard.medium.com/boss-of-the-socs-bots-v3-part-1-3a0d92b851b4)

Video playlist: [Splunk Fundamentals for Users and Power Users](https://www.youtube.com/playlist?list=PL7zWAA-DF0k_sxswRiB7_GUTyI0FoV7lc)

## Further learning

- <https://www.coursera.org/learn/pythonforcybersecurity-introduction>

- <http://docs.splunk.com>
- <http://splk.it/how-to>
- <http://education.splunk.com>
