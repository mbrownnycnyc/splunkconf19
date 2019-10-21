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


## Day 1: Creating Dashboards

* lab:
  * http://100.26.48.46/static/app/search/splunku_lab_files.zip

### orientation

* index=web sourcetype=access_combined
* index-sales sourcetype="vendor_sales"
* index=security sourcetype=linux_secure
* Do not use the search auto-formatter in user preferences SPL editor when editing XML

### references:

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

### Module 1: lab

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



### Module 3: Improving Performance

### Module 4: Customizing Dashboards

### Module 5: Using Drilldowns

### Module 6: Adding Advanced Behaviors & Visualizations