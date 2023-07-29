# Splunk

## Contacts

### Teaching Assistant

Dominic Järmann
E-Mail: <dominic.jaermann@icloud.com>
Telephone: 0787367787

### Contacte de Steve

Oliver Stapleton
<oliver@splunk.com>

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

## Basic Search in Splunk

[Basic Searching in Splunk Enterprise](https://youtu.be/GWl-TuAAF-k)

Video: <https://www.youtube.com/watch?v=GWl-TuAAF-k&list=PL7zWAA-DF0k_sxswRiB7_GUTyI0FoV7lc&index=2>

## Start Splank in Local Computer

In any case, after performing the following steps, navigate to this address in a supported browser: <http://127.0.0.1:8000/>

### Windows

 In subsequent examples and information, replace `$SPLUNK_HOME with C:\Program Files\Splunk` if you have installed Splunk in the default location. You can also add `%SPLUNK_HOME%` as a system-wide environment variable by using the Advanced tab in the System Properties dialog box.

From a command prompt or PowerShell window, run the following commands:

    cd <Splunk Enterprise installation directory>\bin
    splunk start

### Linux

    cd $SPLUNK_HOME/bin
    ./splunk start

## BOTSv3

### Install BOTSv3 Dataset

Download Dataset from <https://github.com/splunk/botsv3>

Install the dataset following the advice from Oliver.

### Download BOTSv3 Apps

Install pre-requisite apps following this source: [Splunk Boss of the SOC v3 Datasets: Your Ultimate Guide to Installation and Configuration for Effective Security Analysis](https://www.linkedin.com/pulse/splunk-boss-soc-v3-datasets-your-ultimate-guide-uday-subramanya-hs).

The dataset is located at: <https://github.com/splunk/botsv3.git>

To check integrity of the files, use the `sha256sum` utility. See [How to take sha256sum of file and compare to check in one line?](https://superuser.com/questions/1312740/how-to-take-sha256sum-of-file-and-compare-to-check-in-one-line) for details.

### Install BOTSv3 Apps

Navigate to `apps >> Manage Apps`, and press the button `Install app from file`.

Download the add-ons specified at
<https://github.com/splunk/botsv3>

[Install an add-on in a single-instance Splunk Enterprise deployment](https://docs.splunk.com/Documentation/AddOns/released/Overview/Singleserverinstall)

## TODO

### Incidents Installing Apps

[Create an overlay chart and explore visualization options](https://docs.splunk.com/Documentation/Splunk/9.0.5/SearchTutorial/Chartoverlays)

### Focus Track Materials

 BOTSv3 environment: <http://3.67.98.121:8000/>

 Username: `powercoders`
 Password: `$H0l1d41s$`

[Boss of the SOC v3 Dataset Released!](https://www.splunk.com/en_us/blog/security/botsv3-dataset-released.html)

 [Splunk Boss of the SOCs (BOTS) V3 — Part 1](https://ellisstannard.medium.com/boss-of-the-socs-bots-v3-part-1-3a0d92b851b4)

Video playlist: [Splunk Fundamentals for Users and Power Users](https://www.youtube.com/playlist?list=PL7zWAA-DF0k_sxswRiB7_GUTyI0FoV7lc)

### Official Splunk Tutorial

- <https://docs.splunk.com/Documentation/Splunk/7.1.9/SearchTutorial/StartSplunk>

- <https://docs.splunk.com/Documentation/Splunk/9.0.5/SearchTutorial/WelcometotheSearchTutorial>
- <https://docs.splunk.com/Documentation/Splunk/7.1.9/Installation/ReadytostartusingSplunk>

## BOTSv2

- <https://samsclass.info/50/proj/botsv2.htm>
- <https://github.com/splunk/botsv2>
- <https://splunkbase.splunk.com/app/4430>
- <https://events.splunk.com/BOTS_2_0_datasets>
- <https://www.splunk.com/en_us/form/through-the-looking-glass-table.html>

## Further learning

- <https://www.coursera.org/learn/pythonforcybersecurity-introduction>

- <http://docs.splunk.com>
- <http://splk.it/how-to>
- <http://education.splunk.com>
- <https://www.splunk.com/en_us/blog/learn/splunk-tutorials.html>
- <https://medium.com/edureka/splunk-tutorial-3e1b5a22e6fe>
