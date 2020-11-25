# Data Visualization - *Group 4*

For our project we decided to explore the relationships between COVID-19, rental inventory, and medium household income throughout New York City's community districts.

Group Members: **Hannan Abid, David Dejesus, Aaron Mui, Lesly Ayala**

Tool Used: **Tableau**

## Visualizations
Below is a list of visualizations included in our final project along with the steps on how to recreate them yourself using Tableau after importing the data:

**Interactive map showing COVID-19 data over time as well as NYC community districts**

1.Drag the "geometry" geographical role located in the "geo_export_af59be5b-5d5a-4b31-8c85-062ea3c14f2b.shp" file onto the "detail" mark to outline NYC's community districts.

2.Drag the "Community District1" string role onto the "detail" mark to detail the community districts on the map.

3.Drag the "Case Count" number role onto the "color" mark to add the total amount of COVID-19 cases on the map. (Feel free to change the color and range by selecting "color" in the dropdown menu in the top right of the color legend.

4.Drag the "Covid Date" date role onto the "filters" card and then select relative date. After that click the special box and then click on Non-null dates. This is important for our "Covid Date Parameter" in order for it to not show areas with no dates associated such as parks and non-residential areas.

5.Right click on the "Covid Date Parameter" and select show parameter in order to enable the date selection drop down menu.

**Line graph showing COVID-19 in NYC over time**

1.Drag the "Count Date" date role into the columns field and then right click on the "year(Count Date) field in the columns and select the "Day" that is formated like so: Month, Day Year

2.Drag the "Case Count" number role into the rows field

3.Drag the "Covid Location" string role calculation into the filters card and then click on true

4.Right click on the "Location Parameter" and click on show parameter to enable the community district selection drop down menu.


**Line graph of NYC Rental Inventory and COVID-19 Cases **

1.Measure names from rentaliinventory_All should be used as a mark. 
2."SUM(Rental Inventory)" and "SUM(Case Count)" should be dragged into the rows field
3."DAY(RENTAL/Covid Data Single Combined)" should be dragged into the columns field

Calculation 3 filter:

IF [Community District (rentalInventory!All)] = [Location Parameter] THEN 'true' ELSEIF  [Location Parameter] = 'All' THEN 'true' END

This filter should be dragged to the filters field and be set to true.
If the community district from the data is equal to the location on the location parameter it returns true.
If the location parameter is equal to ALL it returns all data of neighborhoods and covid data on a graph.
By setting to true, data for specific locations will show up and not other locations. Other locations and ALL will return false.

**Map of Rental Inventory and COVID-19 cases**
1.Geometry from the “geo_export_af59be5b-5d5a-4b31-8c85-062ea3c14f2b.shp” shape file should be set as a mark.
2."DAY(Count Date)" should be set as a mark along with SUM(Case Count) under the "Latittude(generated)" mark
3."SUM(Rental Inventory") should be set as a mark along with DAY(Rent Date) under "Latitude(generated)" 2 mark

Location filter: 

Dragged from tables itself. It shows neighborhood names on the map. 
Null should be excluded from the filter in order to only show non-null values.

Combined Date Parameter: 

IF  [Count Date]=[Combined Parameter] AND [Rent Date] = [Combined Parameter] THEN [Count Date] END

This parameter should be dragged to the filters field.
Uses dates from "Combined Parameter", which is made up of dates from the first of every month starting from April and ending in September



The following **required** functionality is completed:

* [ ] User can **view a list of todo items**
* [ ] User can **successfully add and remove items** from the todo list
* [ ] User's **list of items persisted** upon modification and and retrieved properly on app restart

The following **optional** features are implemented:

* [ ] User can **tap a todo item in the list and bring up an edit screen for the todo item** and then have any changes to the text reflected in the todo list

The following **additional** features are implemented:

* [ ] List anything else that you can get done to improve the app functionality!

## Video Walkthrough

Here's a walkthrough of implemented user stories:

<img src='http://i.imgur.com/link/to/your/gif/file.gif' title='Video Walkthrough' width='' alt='Video Walkthrough' />

GIF created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while building the app.

## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
