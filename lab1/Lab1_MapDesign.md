% Lab 1: Map Design
% Cameron Blevins
% Mapping the Past (Rutgers University, Spring 2016)

##Overview

Today you will learn how to build and design maps using historical data. There are many kinds of tools for making maps, from pen and paper to Geographic Information System (GIS) software. For our purposes, however, we will be using an online mapping and visualization platform called [CartoDB](http://cartodb.com). In the lab, you will be mapping one of the most famous journeys in American history: the Lewis and Clark expedition of 1804-1806 across what is now the western United States. In 1803 the U.S. Government purchased the Louisiana Territory from France, a huge tract of land stretching west from the Mississippi River. Shortly after, the U.S. Government commissioned Meriwether Lewis and William Clark to lead an exploratory trip across the newly acquired territory to map its contents. Over two years, the men traversed the region, reached the Pacific Ocean, and then returned to St. Louis. You will be using CartoDB to build a map their journey.

##Goals

- Become familiar with different types of spatial data
- Learn how to navigate the CartoDB interface
- Build a map and learn how to change its appearance and visual design

##Lab Report
Your lab report should take the form of a Microsoft Word document saved with the filename of "yourlastname_lab1" (inserting your last name). In it, please number your answers to each of the numbered questions below labeled *LAB REPORT*. Email the lab report to: cameron.blevins@rutgers.edu

##The Data

Digital maps can be thought of as layers. The bottom layer is what's called a base map - think of a map of the United States, the state of New Jersey, or the Rutgers campus. Different kinds of data can then be overlaid on top of this base map - ex. roads, rivers, or campus buildings. CartoDB provides you with the base map, but what you need is the data. 

Navigate to 
[https://github.com/cblevins/mtp2016/tree/gh-pages/lab1/lab1_data](https://github.com/cblevins/mtp2016/tree/gh-pages/lab1/lab1_data). This folder contains the raw material you need to create a map. To download a local copy of these files to your computer, you can download a zipped version of this folder at: [https://github.com/cblevins/mtp2016/raw/gh-pages/lab1/lab1_data.zip](https://github.com/cblevins/mtp2016/raw/gh-pages/lab1/lab1_data.zip). Unzip the folder and look at its contents. Notice that there are different types of files (ending in .pdf, .csv, .zip), and that some of them include **-metadata** in their names. These files tell us contextual information about the data - what the files contain, who made them, when they were created, etc. Open up the files with the word "metadata" in its name - these will be your references for understanding the data you'll be working with. In particular, read each of the Overview sections to get a better handle on what you have to make a map.

*LAB REPORT*

@. When were each of these data files created?
@. What were the sources that were used to create these data files?

CartoDB operates "in the cloud," which means that in order to begin creating a map you first need to transfer the local data files on your computer to CartoDB's online servers. Login to CartoDB and click next to your username in the upper right and select "Your Datasets." Then click the button labeled "New Dataset". This page will allow you to either upload a file from your computer or from an online link to a file. Start with uploading 1783treaty.zip and click Connect to Dataset. Once it has uploaded, it will show you the dataset and allow you to view it in two ways: Data View and Map View. Data View shows you the information contained in this file in the form of a table, with each column telling you a different aspect of the data (think of this as the ingredients for a meal). Map View takes that information and plots it in space onto a map (think of this as what comes out of the oven). Click on Map View - this should present you with a map of the boundaries of the United States as it appeared between 1783 and 1803, prior to the Louisiana Purchase. This dataset is what's known as **polygon data**, which is one of three major types of spatial data (polygons, points, and lines).

Now go back to your dashboard (arrow in the upper left corner) and upload **la_pur1.zip** to your CartoDB account using the same steps you did for 1783treaty.zip. This is a similar file containing polygon data, but this file shows the geographic boundaries of the Louisiana Purchase. Click on Map View to see how large this territorial purchase really was.

Next, upload **lewiscla.zip**. If you click on Map View you can see that it is showing the route that Lewis and Clark took on their expedition. Go back to Data View, and notice that this file has much more information than the two previous polygon datasets. Each row represents a segment of their journey, and each column tells you information about that segment. The column "the\_geom" indicates that this is **line dataset**, as opposed to the two previous **polygon datasets** (which you probably could have figured out from that map). But what about the other columns? Some of them you might be able to guess. But for reference, go back to your local folder with the data files (or go to [https://github.com/cblevins/mtp2016/tree/gh-pages/lab1/lab1_data](https://github.com/cblevins/mtp2016/tree/gh-pages/lab1/lab1_data)) and look at the contents of the metadata file for your "lewiscla" dataset. Using this file for reference, examine the Data View for the uploaded dataset **lewiscla** that shows segments of Lewis and Clark's journey and answer the following questions:

*LAB REPORT*

@. How many days did it take Lewis and Clark to travel along the expedition segment number labeled 12?
@. Where did this segment of their journey start and where did it end?
@. Which direction were they traveling?

Finally, upload the last data file: **lewis-clark-sites.csv**. Examine both the Data View and the Map View once it has been uploaded. This is an example of the third kind of spatial data - **point data** - with each row in the table corresponding to an individual location in space. The reason why CartoDB knows that this is a point data file is that it includes two columns labeled "Latitude" and "Longitude". These are geographic coordinates that tell CartoDB where to put that point was on a map. If you examine the dataset's associated metadata file on your computer (lewis-clark-sites-metadata.txt), you'll get more information about the data - including the fact that I modified it from its original format to better suit the purposes of this lab. Use CartoDB's Data View for "lewis-clark-sites" and the accompanying metadata file on your computer to answer the following questions.

*LAB REPORT*

@. Where were Lewis and Clark between October 25-27th, 1805?
@. Using Google or Wikipedia, find an image of this location and insert it into your lab report. 

##Making a Map

You now should have four datasets in your CartoDB dashboard that you can use to build a single map. To do so, switch from **[your username]/Datasets** to **[your username]/Maps** in the upper left-hand corner. Then click the button that says New Map. This will bring you to a page that allows you to specify which datasets you want to include in the map. Click once on all four of your datasets and click Create Map.

Congratulations! You have made your very first basic map! Give it a title in the upper left to replace Untitled. Notice that all four datasets have been layered on top of CartoDB's base map  (two polygon datasets, one line dataset, and one point dataset). Play around with the map - zoom in and out, click on different points or line segments. In the bottom left hand corner, click on "Change basemap" and experiment with the different options until you find one you like. On the right-hand side of the screen there is an expandable set of tabs. These are the layers on your map, labeled 1-4. Click on one of them and it will give you more visualization options for that particular layer. 

Find the layer for **la_pur1**, expand it, and then click on the icon for "wizards" (a paint brush). This will give you different options for coloring, shading, outlining, etc. this dataset. Under "Polygon Fill", change the color to green or another color of your choosing. The menu next to the color option allows you to change the layer's transparency - how "see-through" it is. Try changing this option to "0.5" and notice how the layer's appearance on the map changes. Scroll down and experiment with some of the other visual options for this layer. Be sure and add a label for this layer, using the layer's "name" field. Next, expand the layer for the other polygon dataset of US boundaries between 1783-1803. Switch it to the same color as **la_pur1**, but increase the transparency to 0.8. Add a label.

There are more advanced coloring and display options as well. Right now, the line dataset is a single color, and the viewer cannot tell which *direction* the explorers were moving along that line. Fortunately, the underlying data for this line has that information for each segment. We're going to color the different line segments according to whether Lewis and Clark were traveling *east* or *west* at that point. To do so, expand the point layer and click on the "wizards" icon again. You'll see several different thumbnail images showing different colored lines (labeled Simple, Chloropleth, etc.). Click on "Category" and notice that the line layer has changed into many different colors. What we can do now is tell it to color it according to the information contained in a specific column - in this case, the "westbound" column. Selecting this column from the drop-down will allow you to choose a color for each of its two values of "yes" (meaning the explorers were traveling west) and "no" (meaning the explorers were traveling east). Color the westbound segments blue and the eastbound segments purple.

*LAB REPORT*

@. Using the same steps as you did for the line segments, try to figure out how to color the points from your **sites dataset** so that the points on the westward journey match the color of the line segments for the westward journey, and same for the eastward points and line segments. **Take a screenshot of your newly colored map and insert it into your lab report.**

One of the benefits of making a map in CartoDB is that it can be interactive. For instance, let's say we wanted to the viewer to be able to click on one of the points along Lewis and Clark's journey and find out more information about it. To do so, expand the dataset point dataset in the right-hand pane and click on the "infowindow" icon (a message bubble). From here, you can select which columns of information you want the viewer to be able to see if they either click on or hover their mouse over any of the points. Under the "Click" tab within the infowindow pane, turn on the columns for "arrive" and "depart". Now click on any of the points on the map - it should have a pop-up window showing you the day that the explorers arrived and departed from that location. Now under the "Hover" tab within the infowindow pane, turn on the columns for "details" and "directions". If you hover your mouse over any of the points, it should show you that information about that point in the journey.

There are many, many other ways to change the visual appearance of your datasets. Again, one of the advantages of digital mapping is that you can create animated maps, not just static ones. To demonstrate, expand the **sites** point dataset from the right-hand pane and click the "wizards" icon. Scroll right to look at the different types of ways you can visualize this dataset (ex. Simple, Cluster, etc.). Click on Torque. If your dataset has a column that contains information formatted as dates or times, you can make your map animated. In this case, there are two such columns in our dataset: "arrive" and "depart", corresponding to the day that the explorers arrived at a point and then left that location. If CartoDB hasn't selected one of these options by default under the Time Column, try selecting "arrive". You should see the points moving along your map, with a time slider at the bottom according to the corresponding month/year. Using this slider, you can pause the animation or move it to a different point in time. 

*LAB REPORT*

@. Using the animation, estimate which half of the journey took Lewis and Clark longer to complete - going westward towards the Pacific or eastward back towards St. Louis?
@. Switch your map from Map View to Data View, and if you need to, select the **sites dataset** from the right-hand pane. How many months did it take the expedition to travel from St. Louis to Fort Clatsop (the farthest western point on their journey)? How many months did it take them to travel back from Fort Clatsop to St. Louis?

##Putting It All Together

For your final part of the lab, you will be trying to make a map on your own from scratch. You will be using data that has been compiled by historian [Abby Mullen](http://abbymullen.org/) as part of her research project, [*Encounters in the Quasi-War*](http://abbymullen.org/projects/Quasi-War/). Go to her project website and look at the [map she created](http://abbymullen.org/projects/Quasi-War/), along with [more details about the making the map](http://abbymullen.org/projects/Quasi-War/calculations_text.html). 

Your last assignment for this lab is to recreate her map - not necessarily using the same design or visual layout, but using the same data. For the purposes of this lab, I have lightly modified Mullen's dataset to make it easier to use in CartoDB. You can connect to this modified dataset by going to New Dataset, but then instead of uploading a file from your computer, copy and paste this URL into the right-hand box and click Submit: https://raw.githubusercontent.com/cblevins/mtp2016/gh-pages/lab1/mtp2016_naval_data.csv

Once you've imported the dataset, examine the data and look at the information that Mullen has provided on her webpages to try and figure out what the different columns might mean. Then put this data onto a map and start exploring it. What is interesting to you? What kind of patterns do you notice? What are the different ways you could show these patterns?

@. What are some patterns you noticed about the data while experimenting with different map options?

Select a particular dimension of Mullen's dataset that you would like to illustrate through a map. Do you want to create an animated map of battles over time? Do you want to show the viewer which encounters resulted in victory for different nations? Do you want to create a heat-map to see where encounters were concentrated? After you have decided what aspect of the data you want to focus on, change the visual appearance options for your map to best show the information (note: do not just leave the default options). **Be deliberate about what you want to show and select options that best illustrates that aspect of the data.** I will be offering critiques and feedback on these design decisions, so spend some time thinking about them. 

*LAB REPORT*

@. What is the URL of your final map? (copy and paste)
@. What part(s) of the data did you want your map to show? Why did you choose this aspect of the data?
@. What design choices did you make to best convey this dimension(s) of the data?
@. What did you find most rewarding and most challenging about completing this assignment? Why?

###More Information
CartoDB has a strong set of tutorials and guides to learn how to do more advanced map design: [http://academy.cartodb.com/](http://academy.cartodb.com/)