- [questions for Telemak/David](#questions-for-telemakdavid)
- [things I should know](#things-i-should-know)
- [Intro](#intro)
  - [Training](#training)
  - [.conf Talks](#conf-talks)
  - [My schedule](#my-schedule)
  - [Breakout talks that are interesting](#breakout-talks-that-are-interesting)
  - [tips and tricks](#tips-and-tricks)
  - [Splunk University: Creating Dashboards](#splunk-university-creating-dashboards)
    - [orientation](#orientation)
    - [references:](#references)
    - [Module 1: Creating a Prototype](#module-1-creating-a-prototype)
      - [plan](#plan)
      - [Name the components of a view](#name-the-components-of-a-view)
      - [Compare dashboard and form simple XML syntax](#compare-dashboard-and-form-simple-xml-syntax)
      - [Troubleshoot views](#troubleshoot-views)
      - [Use best practices for creating views](#use-best-practices-for-creating-views)
      - [Identify the primary transforming commands](#identify-the-primary-transforming-commands)
      - [four types of panels](#four-types-of-panels)
      - [ad hoc info](#ad-hoc-info)
      - [Module 1: lab](#module-1-lab)
    - [Module 2: Using Forms](#module-2-using-forms)
      - [Module 2 Lab](#module-2-lab)
    - [Module 3: Improving Performance](#module-3-improving-performance)
      - [Refine searches:](#refine-searches)
      - [Use scheduled reports:](#use-scheduled-reports)
      - [Accelerate reports/data models:](#accelerate-reportsdata-models)
      - [Use the tstats command](#use-the-tstats-command)
      - [Use a global search](#use-a-global-search)
      - [Use tokens](#use-tokens)
    - [Module 4: Customizing Dashboards](#module-4-customizing-dashboards)
      - [Module 4 lab](#module-4-lab)
    - [Module 5: Using Drilldowns](#module-5-using-drilldowns)
    - [Module 6: Adding Advanced Behaviors & Visualizations](#module-6-adding-advanced-behaviors--visualizations)
    - [Additional items:](#additional-items)
- [Monday](#monday)
  - [Keynote:](#keynote)
    - [new products](#new-products)
  - [11AM: SEC2787 - Security Super Session](#11am-sec2787---security-super-session)
    - [Marketing stuff](#marketing-stuff)
    - [Product integration progress](#product-integration-progress)
      - [SOC operations analysis:](#soc-operations-analysis)
      - [Splunk Mission Control](#splunk-mission-control)
      - [Splunk Data Stream Processing (DSP)](#splunk-data-stream-processing-dsp)
      - [Intel dude](#intel-dude)
      - [Splunk ES 6.0 release](#splunk-es-60-release)
      - [Splunk UBA 5.0 release](#splunk-uba-50-release)
      - [Splunk Phantom 4.6 release](#splunk-phantom-46-release)
      - [Upcoming products](#upcoming-products)
  - [12:30PM: FN1945 - Artificial Intelligence got you down? Here’s Machine Learning for Humans!](#1230pm-fn1945---artificial-intelligence-got-you-down-heres-machine-learning-for-humans)
    - [Machine Learning](#machine-learning)
      - [Overview](#overview)
      - [Splunk Machine Learning](#splunk-machine-learning)
      - [MLTK analysis:](#mltk-analysis)
      - [MLTK explanation:](#mltk-explanation)
      - [What you need to work with the MLTK:](#what-you-need-to-work-with-the-mltk)
      - [MLTK use case examples within app dashboard](#mltk-use-case-examples-within-app-dashboard)
      - [Brute force examples](#brute-force-examples)
      - [another example](#another-example)
      - [where do we go from here:](#where-do-we-go-from-here)
  - [1:45PM: SEC1556 - Building Behavioral Detections: Cross-Correlating Suspicious Activity with the MITRE ATT&CK™ Framework](#145pm-sec1556---building-behavioral-detections-cross-correlating-suspicious-activity-with-the-mitre-attck%e2%84%a2-framework)
    - [building behavioral detections](#building-behavioral-detections)
      - [getting started](#getting-started)
      - [risk building and alerting](#risk-building-and-alerting)
      - [finding threats](#finding-threats)
        - [MITRE ATT&CK](#mitre-attck)
        - [resources to build ccontent](#resources-to-build-ccontent)
      - [build risk indexes](#build-risk-indexes)
      - [alerting on risk scores](#alerting-on-risk-scores)
      - [risk incidents rules:](#risk-incidents-rules)
      - [tuning and enrichment](#tuning-and-enrichment)
        - [tuning](#tuning)
        - [enrichment](#enrichment)
    - [take aways](#take-aways)

# questions for Telemak/David
* will they ever expose dashboard XML as git repos for cloud instances, for instance?
* 

# things I should know
* commands
  * `chart`
  * `fillnull`
  * `timechart`
* Need to discuss whether our MSSP SOC will be utilizing our Splunk instance and using Mission Controol
  * Does Hurricane Labs have this capability?
  * Is this a goal?



# Intro

## Training

Fundamentals 1, as well as the architecture training are free and are located on [the training portal](https://www.splunk.com/en_us/training/free-courses/splunk-fundamentals-1.html).  

## .conf Talks

[.conf talks are free to watch for this year and historically.](https://conf.splunk.com/watch/conf-online.html?#/)

## My schedule

* Monday
  * Creating Dashboards
* Tuesday
  * 11AM: SEC2787 - Security Super Session
  * 12:30PM: FN1945 - Artificial Intelligence got you down? Here’s Machine Learning for Humans!
  * 1:45PM: SEC1556 - Building Behavioral Detections: Cross-Correlating Suspicious Activity with the MITRE ATT&CK™ Framework
  * 3PM: FN1054 - Best Practices and Better Practices for Admins
  * 4:15PM: FN1206 - The path to operational enlightenment. An introduction to wire data with Splunk Stream.
* Wednesday
  * 11:15AM: SEC2534 - Security visibility through Windows endpoint analytics
  * 12:30PM: SEC2366 - What's New in Splunk for Security
  * 1:45: SEC1927 - ATT&CK™ Yourself Before Someone Else Does
  * 3PM: SEC1391 - Building a Security Monitoring Strategy 2.0
  * 4:15PM: IT1761 - Service and Asset Discovery with Wire Data
* Thursday
  * 10:30AM: SEC1525 - Finding Mr. Robot: Jump Start Your SOC and Operations Teams
  * 11:45AM: SEC1179 - The House Always Wins: Using Splunk Enterprise to Fight Data Exfiltration From Insider Threats
  * 1PM: IoT1103 - Applying Splunk Essentials for Predictive Maintenance
  * 2:15PM: IT1970 - Tracking Micro Services with Splunk

## Breakout talks that are interesting


## tips and tricks

* shift-ctrl-E will expand out macros
* macros are located in Settings > Advanced Search > Search macros


## Splunk University: Creating Dashboards

* lab:
  * http://100.26.48.46/static/app/search/splunku_lab_files.zip

### orientation

* index=web sourcetype=access_combined
* index-sales sourcetype="vendor_sales"
* index=security sourcetype=linux_secure
* Do not use the search auto-formatter in user preferences SPL editor when editing XML

### references:

* Splunkbase app: https://splunkbase.splunk.com/app/1603/
* [Data Structure Requirements for Visualizations](http://docs.splunk.com/Documentation/Splunk/latest/Viz/Datastructurerequirementsforvisualizations)
* [Visualization Reference](http://docs.splunk.com/Documentation/Splunk/latest/Viz/Visualizationreference)
* [Transforming Commands](http://docs.splunk.com/Documentation/Splunk/latest/SearchReference/Commandsbytype#Transformingcommands)
* [Statistical and Charting Functions](http://docs.splunk.com/Documentation/Splunk/latest/SearchReference/CommonStatsFunctions)


### Module 1: Creating a Prototype

#### plan

1) discuss key metrics, time frames, etc... draw a storyboard
2) add interacivity
3) get stakeholders to sign off
4) improve performance
5) get feedback and customize

#### Name the components of a view

* every page is a view:
  * dashboard
  * forms
* Each view built from:
  * XML
  * html
  * css
  * javascript

#### Compare dashboard and form simple XML syntax

* dashboard
  * most common type of view
  * limited user input
  * default interactive features
* form
  * enter values from a variety of inputs
  * user input  stored as token

* escaping characters
  * can be used with HTML replacement entiteis (such as `&amp;`)
  * or can use `CDATA` tags
    * the professor has a preferences for `CDATA` tagging
      * `CDATA` tags are within an XML/HTML tag.

* XNL Source Editor is built in to the web

#### Troubleshoot views

* generally about troubleshooting efficiency of searches
* job inspector

#### Use best practices for creating views

* settings> user interface> views
* using panels
* There are HTML panels (see below), you can convert XML dashboards to HTML... or you can embed HTML in the XML
* Panel visualization types:
  * chart
  * event
  * map
  * single value
  * table
  * custom visualization
  * html

#### Identify the primary transforming commands

* stats
* chart
* top
* rare

#### four types of panels

* inline
  * search runs when the dashboard is loaded
  * query is built directly into the source via the `<query />` tag
  * Clone to inline is exposed via the View Report menu.
* report
  * 
* prebuilt
  * this entity is reusable
  * it is immutable outside of the prebuilt panel... immutable within reports, etc
  * can convert other panel entities to prebuilt panels
  * free standing object, can apply to one or more dashboards... basically the code without the dashboard.
  * Settings> USer Interface> Pre-built panel -> new
    * you can take some panel code from a dashboard and copy the source and paste it into this part.
    * Once created, prebuilt panels can be inserted into a new dashboard> "add prebuilt panel"
    * prebuilt panels are locked down in the dashboard editor!  They are tied directly back to the pre-built panel itself.
* clone
  * this entity is reusable.
  * it is mutable.

#### ad hoc info

* you can create a dashboard from a report by adding the report as panel
* if a report is scheduled, then the report that's pulled into the dashboard is the cached copy... not a re-run.

#### Module 1: lab

* covers:
  * creating prebuilt panels
  * creating a datamodel (with data restrictions to eliminate `NULL`)


### Module 2: Using Forms

* general notes
  * the xml entity is no logner `<dashboard>` it is `<form>` when sub tags are `<input />`
  * when building drop down `dynamic options` always use highly efficient searches, such as an `inputlookup`.

* References:
  * [Token Usage in dashboards](http://docs.splunk.com/Documentation/Splunk/latest/Viz/tokens)
  * [Token Filters](http://docs.splunk.com/Documentation/Splunk/latest/Viz/tokens#Token_filters)
  * [Create and Edit Forms](http://docs.splunk.com/Documentation/Splunk/latest/Viz/FormEditor)

* Identify types of form inputs
  * text
  * dropdown
  * radial
  * multi-select
* Describe how tokens are created and used
  * you can optionally tokenize inputs
  * the options is surfaced while creating the _input_
    * multi-select inputs:
      * this is a unique case:
        * provide a `token prefix` and `token suffix`
          * You probably want to use `(` and `)`
        * provide a `token value prefix` and `token value suffix`
          * You probably want to use something like `FIELD="` and `"` respectively
        * provide a `delimiter` to split up your tokenized items
          * you probably want to use `OR` (when using multi-select) 
* Use tokens with form inputs
  * you can use the `<set>` and `<eval>` to set tokens in the code
  * tokens are like variables, and are assigned to an input, and are interpolated into searches, etc, by using `$[token_name]$`
    * note you probably want to nest `$tokentized_things$` in double quotes
  * Tokens have filters also...
    * `$tokenized|s$`
      * wraps token in quotes
        * __VALUE ADD__:  Do this for all tokenized fields in SoT dashboard
    * `$*|h$`
      * escape HTML values
    * `$*|u$`
      * encode url values
    * `$*|n$`
      * no encoding
    * `$*|$$`
      * escape the `$` special character so that it represents a `$` character
    * custom filters... built your own with javascript
      * You can not combine filters
      * Instead create a custom filter and then you can provide extended functionality.
  * There are tokens in the global environment:
    * `$env:user$`
    * `$env:user_realname$`
    * `$env:user_email$`
    * `$env:app$`
    * `$env:locale$`
    * `$env:page$`
    * `$env:product$`
    * `$env:version$`
    * `$env:view_label$`
    * `$env:is_enterprise$`
* Create cascading inputs
  * 
* Define types of token filters
  * 

#### Module 2 Lab



### Module 3: Improving Performance

Covered thoroughly in the ninja.pdf, also take the architecture class for free.

Additional notes:
* data sets are entities within a data model.
* data sets are addressed by `[datamodel].[dataset]`

#### Refine searches:
* Limit your search to a specific time window and quantity of data retrieved
* Use the most efficient command for the use case
* Make the base search part of a global search, as specific as possible
* Avoid using `NOT` (`!=`) expressions
#### Use scheduled reports:
* if you schedule a report, then create a panel based on this report, then the dashboard panel pulls data from reported cache.
* Remember that saving as a dashboard panel automatically places it as an inline panel... with the query embedded into the dashboard, which executes at render time.
#### Accelerate reports/data models:
* Use Acceleration --> create a tsidx file for some subset of events
* tsidx contains pre-calculated statistic data... it's faster to access this data than parsing _raw or performing search time field extraction.
* The options to Accelerate Report is available under searches/reports options.
* Acceleration can only function on streaming pipelines, for instance, 
* for instance, `*|dedup` can't be used  

Here are some additional notes on accelerating data models:
    * accelerating data models require administrative privileges
    * should be reserved for data models that are heavily used.
    * The generated summeries take up space.
    * after creation the following occurs:
      * splunk begins building summeries that span the range you've specified.
      * Splunk builds them in indexes with events that contain the fields specified.
      * Splunk then searches every five minutes to update the existing summeries
      * Splunk runs a maintenance process every 30 minutes to remove outdated summeries.
      * The above times can be adjustedd by a splunk admin.

#### Use the tstats command
* refer to ninja.pdf and summerize data.
* You can take just the tsidx meta data only.  it's a boolean on `| tstats summeriesonly=true`.  You can backfill from the last time the stats were generated by using `| tstats summeriesonly=false`.
#### Use a global search
* post-processing
* Global searches are results in dashboards that other panels can refer to.
  * They are effectively the result feeder... they are at the beginning of the pipeline.
  * embed `<search id="a global search">` tag as a `<query>,` at the beginning of the dashboard and is specified per panel.
    * to specify in a panel use: `<search base="a global search">`
* This generates a `data cube`
  * use `fillnull` command to fill `$null` or `none` values... in an event search.  This affects all results in scope of the search.
#### Use tokens
* refer to the previous module.


### Module 4: Customizing Dashboards

* Dashboards can be edited in a few ways:
  * in the dashboard UI
  * in Settings> User Interface> Views
  * edited on the SH: with `$SPLUNK_HOME/etc/`, which requires a restart of `splunkd`
  * via the REST API
* Modify chart and panel colors
  * usually colors used in charts vary.
  * stuff like `<option name="charting.fieldColors">{""}</option>`
* Event Annotations
  * `<search type="annotation">` and a contained query
    * you must provide `eval annotation_category=message` and `eval annotation_label=message`
  * this query layers on top of the existing visualization
    * Note that `$time.tok.earliest$` and `$time.tok.latest$`
* Tables
  * Formatting options on stats data results... such as `table`.
    * You can format coloring per columm on a `table` for instance.
* Trellis
  * Multiple instances of a visualization, where each instance shows values for just one category
  * this can be over laid either by item, or flipped around
* For each panel/search visualization, you can modify panel link buttons (the little hover icons at the bottom)
  * Each of these is a setting:
    * link.visible: the whole panel
    * refresh.time.visible, etc etc
* Disable search access features
* Define Simple XML attributes
* Set panel refresh and delay times

#### Module 4 lab


### Module 5: Using Drilldowns

### Module 6: Adding Advanced Behaviors & Visualizations

### Additional items:
* remember datacubes
* check out summary indexes


# Monday 

## Keynote:

### new products

* the CTO presented several new products that seem interesting.


## 11AM: SEC2787 - Security Super Session

### Marketing stuff

* Speaks about some marketing stuff related to the past few years at splunk .conf and where splunk as a company is positioning itself within the security market.  It is the #1 SIEM.
* splunk is positiining itself to be the centralized point of data, analyitics (including an expansion into AI and ML), and automate.

### Product integration progress

* former Phantom CEO speaks
* Splunk's strategy is to integrate all products to provide coverage across the SOC: analyze, collaborate, remediate/orchestrate.

#### SOC operations analysis:

* Splunk covers the SOC work flow / security event flow:
  * ingest:
    * ES
  * detect:
    * ES
    * UBA
  * presdict:
    * UBA
  * automate
    * Phantom
  * orchestrate
    * Phantom
  * recommend
    * Phantom
  * collborate:
    * ES
    * Pahntom
  * investigate:
    * ES
  * manage cases
    * Phantom
  * report: ES
* apply the following items:
  * AI
  * ML
  * Content
* Product: Splunk Mission Control == the solution to SOC coverage
  * Phantom
  * UBA
  * ES

#### Splunk Mission Control

* themes for coverage of the event lifecycle:
  * interconnect data, analysis an ops
  * embeded automation
  * in context
* Cloud based platform == interconnects directly to cloud products
  * splunk ES
  * Splunk UBA
  * Phantom
    * Automation broker resides on prem
      * this allows automations to affect on prem systems.
  * splunkd
* Mission Control UI
  * very nice UI
  * Playbook visualization of execution.
  * playbook editor is a flow-based programming IDE
  * You can overlay and leverage framework based flows (such as NIST 800)
  * Surface additional data, such as threat intel/risk scores

#### Splunk Data Stream Processing (DSP)

* this displaces kafka.
  
#### Intel dude

* they implemented and went live with SOC in splunk within 5 weeks.
* [insert architecture image here]
* supports boringtechnology.com strategy
  * but also should be using products that are universally used
* enforces stream processing

#### Splunk ES 6.0 release

* Assets and identities enhacement
* MLTK powered search
* Investigations reporting
* Licensing
  * UBA is most easily licensed

#### Splunk UBA 5.0 release

* custom ML models
* HA/DR warm standby
* Enhanced device management
* new data category
  * cloud file sharing
  * database
  * badge access
  * printer

#### Splunk Phantom 4.6 release

* Phantom Mobile
* AWS Elasticity
* SHC for Search
* ITSI Monitoring
* 300 apps, 1900+ actions
  * Apps are open sourcing
    * starting with 33
* Licensing
  * seat based
  * no more limits on
    * event processing numbers
    * use case executions

#### Upcoming products

* Analytics:
  * cloud data sources
    * SignalFX: cloud stuff
    * Omnition: container stuff
  * stream processing (DSP)
    * integration with ML/AI
  * Data Fabric Search (DFS)
    * utilizing search across many data lakes

## 12:30PM: FN1945 - Artificial Intelligence got you down? Here’s Machine Learning for Humans!

### Machine Learning

#### Overview

* ML started in 1822: lovelace and babbage
  * 1959: arthur samuels
  * Contemporary: Tom Mitchell / CMU
* not great for data with no pattern
* Definite ML and AI
  * ML: the process of teaching a computer to determine an outcome based on the data it is given.
  * AI: when a machine can do a task that requires human intelligence.
    * We are not doing this.
  * supervised learning: teaching by example
  * unsupervised learning: uses algo to indentify patterns

#### Splunk Machine Learning

* Core Platform Search has ML built-in:
  * SPL function `anomalydetection`...  built-in to baseline SPL!
  * `Patterns` tab in the results
* Premium Solutions
* Machine Learning Toolkit (MLTK)

#### MLTK analysis:
* anomaly detection
  * deviation from past behavior
  * deviation from peers
  * unusual change in features
  * ITSI MAD Nnomaly Detection (premium solution)
* Predictive analytics
  * predict seervice health score prducting churn
  * predicting events
  * trend forecasting
  * detecting influencing entities
  * early warning of failure: predictive maintenance
* Clustering:
  * identify peer groups
  * event correlation
  * reduce alert noise
  * ITSI Event Analytics (premium solution)

#### MLTK explanation:

* Assitants:
  * guided model building, testing and deployment for common objectives
* showcases
  * interactive examples for typical IT, security, business and IoT use cases
* Algos
* ML commands
* ML-SPL API
* Python for Scientific Computer library

#### What you need to work with the MLTK:

* splunk instance
* pythin for scientific computing
* MLTK
* Dataset and use case
* Domain Generation Algorithms (DGA) app:
  * waht it does: phishing use cases... who what where based on the FQDN in embedded links.
  * URL toolbox App
  * 3D Scatterplot
  * Parallel coordinates
  * there are other TAs for URLs and other stuff.

#### MLTK use case examples within app dashboard

* remember to use `anomalydetection` SPL function
* install MTLK
* go to the MLTK
* go to Showcase tab
* focus on detection outlier for instance

#### Brute force examples
* example details: brute force
  * sysmon derived data... reduced data: event ID 4625
    * the progression of a brute force attack:
      * step 1: find user name == results in "bad username" errors
      * step 2: find password == results in "badd password" errors
      * step 3: nothing == the attacker has gained access.
  * take the events and put them into bins:
    * `index=sysmon eventID=4625 | bin _time span=1h | stats count as logins by _time`
  * go into MLTK --> experiments tab
    * detect numberic outliers, click on it
    * create new experiment
    * paste `index=sysmon eventID=4625 | bin _time span=1h | stats count as logins by _time` into the search
    * field to analyze: logins
    * threshold methods: try them all see what helps
      * median absolute deviation
    * threshold multiplier: controls what is an outlier... accept default generally, but you can try to increase... this is reflected as a sahded area on data and outliers
    * you can then save in the upper right
    * once saved, and oou work, your experiement history

#### another example

* Go to MLTK --> Experiments
  * smart forecasting icon> new
  * datasets> specialdays
    * VALUE ADD: populate the specialdays
  * pick a dataset> next
  * add preprocessing step (this would be specialdays, etc)
  * Smart forecasting
    * edit> pick a field

#### where do we go from here:

* Mess with the MLTK
* splunk blogs categories:
  * machine learning blog
* user guide for MLTK.
* ML classes on udemy
* YouTube splunk channel
* Splunk education
  * advanced system: splunk for analytics and data science


## 1:45PM: SEC1556 - Building Behavioral Detections: Cross-Correlating Suspicious Activity with the MITRE ATT&CK™ Framework

### building behavioral detections

#### getting started
* logs and risk indexes
  * log types:
    * network logs: proxy, firewall, IPS, HTTP and DNS
      * Splunk and CIM compliance
      * risk objects:
        * IP is not reliable
        * if necesary, build enrichmsent macros
          * use the `lookup` command
          * macro: `identify_user` `identify_asset` and `enrich_user`, `enrich_asset`
    * endpoint logs
      * EDR and/or sysmon
        * event IDs:
          * 1 (process creations)
          * 3 (network connections)
          * 7 (DLL loads)
          * 8 (CreateRemoteThread process ingestion)
          * 10 (ProcessAccess cred dumpings)
          * 11 (FileCreate)
          * 12,13,14 (RegistryCreatoOrDelete, RegistryValueset, RegistrKeyValueRename)
          * 17,18 (Pipe Created, Pipe Connected)
      * WEL (refer to malwarearchelogy.com)
        * auth and permissions on DCs
        * sysmon, disable:
          * 4688, 4657, 4663, 5156
        * powershell logging
          * make sure you create exceptions

#### risk building and alerting

* risk indexes: watch jim apger + stuart mcintosh conf18 talk "say goodbye to your big alert pipeline, and say hello to your new risk-based approach"
  * ties together many data sources
  * normalized event logs
  * enrish user/host data
* Build to a summary index, add useful metadata and analyst context, events don't need to build risk, can provide situational awareness.

#### finding threats

##### MITRE ATT&CK
* pros/cons
  * pros:
    * visualize overall defense against
    * pinpoint high valu investments in security data soruces and content development
  * cons:
    * advanced techniques hide in noisy log sources
* break down:
  * tactics give us categories of activity:
    * techniques offer specifics of activity
    * not that you will find things that match tecniques, but more enrichment/correlation is needed to reduce false positives.
* develop searches for techniques
  * match a use case, then pipe it into valueable evals
    * add `* | eval mitreAttack` 
    * `risk_message`
    * `risk_infromation`
    * `risk_scorecombined`

##### resources to build ccontent
* https://lolbas-project.github.io
* https://gtfobins.github.io
* search splunk blogs for "staff picks for splunk security"
* https://github.com/olafharlong/threathunting
* search splunk blogs for hunting with spliunk the basics on splunk blog

#### build risk indexes
* build indexes: summary indexes
* alerting
  * search events in the rick index by user or host
  * slide data to find potentially malicious activity
  * monitor and adjust enrichmena to tune
  * add useful metadata for anlayst
* `risk_scorecombined` macro breakdown
  * increase risk for users and assets
    * use cases:
      * vulnerabilities: crit and high
      * silo
      * asset base risk
      * user departures
      * user data access risk
  * risk_mod_count_combined = risk_mod_count_sys + risk_mod_count_user
  * calculate risk_score

#### alerting on risk scores
* risk score exceeds thresholds
* multiple MITRE tastics
* high number of unique ATT&CK techniques
* sudden increase in ATT&CK techniques
* Suddent significant increase in risk score types
* risk events from numberous sourcetypes
* run over a timespan: 24 hours, 7 days, 30 days.

#### risk incidents rules:

* schema accelerated event search <--research this... may be as efficient as a `tstats`
* use `eventstats`, `makemv` to parse the manaully generated fields mitreAttack, risk_information, etc


#### tuning and enrichment

##### tuning
* tune risk incident rules with comfirmed incidents from standard alerts
* tune risk building events by slicing up your risk index for insight
  * remove users for instance
  * consider including an `eval`ed field like `adjustImpact` and processing this within your risk building
* red team is your best friend
* reduces:
  * risk lets you retain potentially useful "noise" as baselines and context
  * trim useless noise, but lean towards downgrading severity of risk
  * checkout `mvexpand` since we used `makemv` earlier

##### enrichment
* include enrichment of data within events in your risk table when you discover it.
  * `| lookup miteenrichment.esv * OUTPUT *`
    * store enrichment data as lookuptables, then use `OUTPUT` to output fields

### take aways
* enrichments increase context
* tuneing is a murder
* 