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

# questions for Telemak/David
* will they ever expose dashboard XML as git repos for cloud instances, for instance?
* 

# things I should know
* commands
  * `chart`
  * `fillnull`
  * `timechart`



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
* 