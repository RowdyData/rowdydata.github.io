---
title: "Recipe: Spaghetti à la Hivos"
fa-icon: fa-list-ol
---


Spaghetti à la Hivos
====================

Showing Hivos’ partner network using IATI data.

![preview]


Begin with the end in mind
==========================

_Think of what you’d like to show, what kind of data do you need to make that
possible and check if you have the right data._

We want to show the network of partners Hivos works with, and get an impression
of the budgets they work with.

You will need these tools:

 - [Open Refine][openrefine]: a tool to manipulate data.
 - A text editor to look at the raw data. For instance [Notepad++][notepad]


Get your ingredients (the data)
-------------------------------

Go to the [IATI Registry][iatiregistry] and find and copy the link to the [Hivos
actvities file][hivosdata]. Or use [a local copy of the data][hivoslocal].


### Quick check

We need to check if Hivos includes implementing partners in its IATI data set.

We open the data file either in the preview on the IATI Registry or in our text
editor, and look at the data to see if there are elements like below – which is
the case.

```xml
<participating-org role="Implementing">...</participating-org>
```


### Set up an Open Refine project

1. Start your Open Refine: it will open in your browser.
1. Select _Create a new project_. Under _Get the data_ you can either:
  * Choose _Web address_ and paste the link to the Hivos file. (Hivos has a
    quirk: the actual link should start with **https** instead of **http**)
  * Or choose _This computer_ and upload your local copy of the Hivos data.
1. Click _Next_, and select <code>iati-activity</code> as the element to load.
  ![hivos-1]
1. Then click the _Create project_ button in the top-right corner.

You will now see something similar to a spreadsheet, but with a choice to view
the data as either **records** or **rows**. Records can have multiple rows. The
**number of records** should match the number of **activities** in the file.


### Analyse the data

Let’s analyse the data Hivos has included in their IATI file. You can easily do
this using facets and filters.

#### Countries

1. At the top of each column you’ll find an arrow pointing downward that offers
  you a range of powerful options to analyse and edit the data in that column.
  - Go to the column near the end, with the header
  ```iati-activity - recipient-country```
  - From the dropdown menu, choose _Facet > Text facet_

1. On the left-hand side, you’ll now see a box showing all the different
  values in this column.
  - There are many different countries in the list.
  - There are a couple of "Regional: ..." entries.
  - There are "(blank)" entries.

1. An activity may happen in multiple countries: a **record** may contain
  multiple rows, each row containing a single country. We'll check if that is
  the case with Hivos by joining those names into a single cell.
  - Again click the arrow for the dropdown menu in the country column, and
    select _Edit cells > Join multi-valued cells..._
  - A comma as separator is fine.
  - The country facet on the left is updated: we can inspect the values to see
    if there are activities with multiple countries. For Hivos, this is not the
    case.
  - We can press Ctrl-Z to undo the previous step.


#### Budgets

1. Towards the end there also is a column
  ```iati-activity - budget - value - currency```
  Again, choose the menu _Facet > Text facet_

1. On the left-hand side, you'll see Hivos uses different currencies. something
  to take into account later on.


Shape and clean the data
------------------------

Now we're going to shape the data, using [Open Refine][openrefine].

1. Find the column <code>iati-activity - iati-identifier</code>, click the
  arrow and select _Edit column > Move column to beginning_

1. Notice how in the top-left corner the _Undo / Redo_ tab now shows a **1**
  <br>![hivos-2]

1. When you click the tab, you will see all the _transformations_ you’ve made so
  far. Here you can easily undo and redo your steps. Feel free to play around,
  showing or hiding columns, changing things!

1. Also notice the buttons _Extract..._ and _Apply..._. With _Extract..._ you
  have access to the code that Open Refine produced to execute your
  transformations. You can copy this code and, with _Apply..._, re-use it in
  future projects.

We will make extensive use of the _Apply_ button to let you perform steps in the
recipe.

To follow the recipe, go back to the original data by clicking on “0. create
project”. The columns you removed or changed are back again.

### Select relevant columns

Either follow these steps, or use _Apply..._ the code below.

1. In the top-left column of the data ("All"), select _Edit columns > Re-order/
  remove columns..._
1. Drag the columns we are not interested in to the right-hand pane.
1. Re-order the columns in the left-hand pane, to end up with this list:
  - ```iati-identifier```
  - ```iati-activity - title```
  - ```iati-activity - sector```
  - ```iati-activity - sector - code```
  - ```iati-activity - sector - percentage```
  - ```iati-activity - participating-org```
  - ```iati-activity - participating-org - role```
  - ```iati-activity - budget - value```
  - ```iati-activity - budget - value - currency```
  - ```iati-activity - recipient-country```
  - ```iati-activity - recipient-country - code```
1. Click _OK_

You can also click the _Apply..._ button, and copy and paste the code below:

```json
[
  {
    "op": "core/column-reorder",
    "description": "Reorder columns",
    "columnNames": [
      "iati-activity - iati-identifier",
      "iati-activity - title",
      "iati-activity - sector",
      "iati-activity - sector - code",
      "iati-activity - sector - percentage",
      "iati-activity - participating-org",
      "iati-activity - participating-org - role",
      "iati-activity - budget - value",
      "iati-activity - budget - value - currency",
      "iati-activity - recipient-country",
      "iati-activity - recipient-country - code"
    ]
  }
]
```

We're not interested in funding partners, just in implementing partners, so we
choose to select and remove funding partners now:

1. Under _iati-activity - participating-org - role_, select "Funding" and then
remove all matching rows.
<br>![hivos-3]

1. Or in an _Apply..._ phrase:

```json
[
  {
    "op": "core/row-removal",
    "description": "Remove rows",
    "engineConfig": {
      "facets": [
        {
          "invert": false,
          "expression": "value",
          "selectError": false,
          "omitError": false,
          "selectBlank": false,
          "name": "iati-activity - participating-org - role",
          "omitBlank": false,
          "columnName": "iati-activity - participating-org - role",
          "type": "list",
          "selection": [
            {
              "v": {
                "v": "Funding",
                "l": "Funding"
              }
            }
          ]
        }
      ],
      "mode": "record-based"
    }
  }
]
```


[openrefine]: http://openrefine.org/download.html
[notepad]: http://notepad-plus-plus.org
[iatiregistry]: http://iatiregistry.org
[hivosdata]: http://iatiregistry.org/dataset/stichting_hivos-data001
[hivoslocal]: hivos-iati-activities.xml
[preview]: preview.png
[hivos-1]: hivos-1.png
[hivos-2]: hivos-2.png
[hivos-3]: hivos-3.png
