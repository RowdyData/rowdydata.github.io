---
title: "0 to IATI in 15 minutes"
name: 0-iati-15-min.slides
description: >
  Quick introduction into the basics of IATI, and what you will encounter when starting to produce IATI data.
fa-icon: fa-desktop
layout: slides
transition: convex
---

{% include slides-start %}
<!-- first column -->

{% include slides-start %}
# 0 to IATI in 15 minutes

{% include slides-next %}

![](/pix/iati-pre.png)

{% include slides-next %}

![](/pix/iati-post.png)

{% include slides-next %}

# IATI Standard

To exchange comprehensive, forward-looking data on development activities.

Under multi-stakeholder governance.

### Evolving standard

- Version 1.01 in February 2011
- Version 1.04 in May 2014
- Version 2.01 in January 2015
- Version 2.02 in December 2015

{% include slides-next %}

from presentation...

![](cordaid-example.png)

{% include slides-next %}

...to raw data

~~~xml
<iati-activity default-currency="EUR"
  last-updated-datetime="2015-02-12T09:09:25+00:00" xml:lang="en">
  <iati-identifier>NL-KVK-41160054-111227</iati-identifier>
  <title>Strengthening youth voices in peace building</title>
  <description type="1">Increased voice and participation of youth leaders on
    peace and security</description>
  <description type="1">UNOY Peacebuilders and Cordaid will work together to
    strengthen the collective voice of youth to convince key players such as at
    the UN on the vital role of young community leaders in building resilient
    communities. The program will provide capacity and resources to illustrate
    best practices and to lobby for involving youth in decision making on peace
    and security processes (similar to UNSCR1325).</description>
  <activity-status code="2">Implementation</activity-status>
  <activity-date  iso-date="2014-06-01" type="start-planned"/>
  <activity-date  iso-date="2015-12-31" type="end-actual"/>
  <reporting-org ref="NL-KVK-41160054" type="21">Stichting Cordaid
  </reporting-org>
  <participating-org ref="NL-1" role="Funding" type="10">Dutch Ministry of
    Foreign Affairs</participating-org>
  <participating-org role="Implementing" type="21">UNOY Peacebuilders
  </participating-org>
  <participating-org ref="NL-KVK-41160054" role="Accountable" type="21">Cordaid
  </participating-org>
  <budget type="1">
    <period-start  iso-date="2014-06-01"/>
    <period-end  iso-date="2015-12-31"/>
    <value value-date="2014-06-01">126974</value>
  </budget>
  <budget type="1">
    <period-start  iso-date="2014-06-01"/>
    <period-end  iso-date="2015-12-31"/>
    <value value-date="2014-06-01">1048</value>
  </budget>
  <!-- ... -->
</iati-activity>
~~~
{: .stretch}

{% include slides-next %}

## Your starting point?

![](starting-points.png){: .col-md-7 .col-md-offset-1}

(but don't stop there!)
{: .col-md-12}

{% include slides-end %}

{% include slides-next %}
<!-- next column -->

{% include slides-start %}

# How?

{% include slides-next %}

# Steps to take

### Start a team

Implementation schedule

### Scope and plan

### Get the data in shape

### Publish and use

Organisation and Activities files

{% include slides-next %}

# Implementation schedule

![](/pix/iati-implementation-schedule.png)

{% include slides-next %}

# Organisation File

![](/pix/iati-organisation-file.png)

{% include slides-next %}

# Activities File

![](/pix/iati-activity-file.png)

{% include slides-end %}

{% include slides-next %}
<!-- next column -->

{% include slides-start %}

# Implementing IATI

### Organisational

Why, with whom?

What to exclude?

### Legal

Liability, rights, security?

### Technical

Which data, which tools?

{% include slides-next %}

# With whom?

### Staff

- Form an "open data team"
- Involve multiple disciplines

### Partners

- Who owns the data?
- What can they do with your data?

### Donors

- What do they want?
- What do they offer?

{% include slides-next %}

# Exclusion policy

### “Open, unless”

- International relations
- Safety and security
- Personal information
- Commercial information
- Legally excluded
- Threshold values

{% include slides-next %}

# Licenses

### Intellectual property rights

Copyright and Database rights

### Right to reuse

For IATI: public domain or attribution-only

### Liability

Disclaimer/proclaimer

{% include slides-next %}

# Which data?

### What is an "activity"?

- Programme, project, unit, ...

### Which programmes or projects?

### Which details?

- Geographic locations?
- Targets and results?
- Budgets and disbursements?
- Commitments and expenses?

{% include slides-next %}

# Which tools?

### Online tool (AidStream)

No IT capacity needed but manual and extra work

### <del>Convert spreadsheets</del>

Not yet available for IATI 2.01 or 2.02...

### IATI platform (Akvo, DevResults, ...)

Fit your work in their model

### Integrated with your own systems

Adapt your own model to produce IATI

{% include slides-end %}

{% include slides-next %}
<!-- next column -->

{% include slides-start %}

# Next...

## Ok, I have an Activities File.

## Now what?

![](/pix/iati-activity-file.png){: .col-md-5}
![](/pix/iati-post.png){: .col-md-5 .col-md-offset-2}
{% include slides-end %}

{% include slides-end %}
<!-- close columns -->
