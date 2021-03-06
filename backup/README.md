
# Data Visualization and D3.js: On-Time Arrival Stats by Airport and Year 
by Mohammad Yaqoob for Udacity's [Data Analyst Nanodegree](https://www.udacity.com/course/viewer#!/c-ud507-nd)

## Summary

This data visualization is designed to shows which airlines will have 80% or greater On-Time Arrival Rates for a selected Airport and Year.  I also wanted to communicate the story that user selected airport and year, on average how much the categories of security, carrier, and weather impact airlines performance by graphing their averages by months, allowing users to see what factors contribute the most to airpot and airline delays.  The data is downloaded from [RITA](http://www.transtats.bts.gov/OT_Delay/ot_delaycause1.asp?display=download&pn=0&month=12&year=2015)  

## Design

After downloading the data from [RITA](http://www.transtats.bts.gov/OT_Delay/ot_delaycause1.asp?display=download&pn=0&month=12&year=2015) I decided to open the csv file to look briefly into the data.  There was nothing otu of the ordinary and the data look pretty crisp and clean.  Fortunately, I didn't need to perform any data cleaning and wrangling with this data set.

### Exploratory Data Analysis 

I used d3.csv to read in the csv file for exploratory data analysis.  The initial plot did not look to deliver the relationship that I was looking for i.e. airlines on-time greater or equal to 80% and categories contributing to on-time performance for airport and airlines as shown in the following graph.

<img src="../master/img/EDA1.PNG" />


Using the provided data, it can be sliced and diced to address my question i.e. "For a given airport and year, which airlines are 80% or greater on-time and how factors like weather, security, and carrier delay impact their performance.

## Data Visualization using dimple.js

I decided to improve upon the initial data visualization further using  **D3.js** and **dimple.js** using iterative design design and analysis.

Next, I modified graphing options to plot all airlines and this was clearly very busy graph too. The scatter plot by itself did not show anything meaningful or distinguishable trends as shown below.

<img src="../master/img/EDA2.PNG" />



Next, I decided to add a line chart with multiple series that will show different trends across different airlines.  I first produced a cursory plot to explore this idea the plot shows on-time trends for the airlines with most airlines on-time rate greater than 50%:

<img src="../master/img/EDA3.PNG" />


Even though plot is clearly busy, it does show some airline on-time trends i.e. effect of Weather.  As we see the On-time performance degrade in certain months that one can relate to weather impact.  This chart is satisfactory in visualizing the this trend for the airlines arriving at the selected airport during the selected year.  It shows how various airlines improved or worsened from month to month, and which airlines performed better for the selected year.  

In order to address the second part of the question as to what factors impact the on-time arrival and how , I decided to look into plotting weather, security, and carrier on-time aveages for the month. 

Using inspiration from examples at [dimplejs.org](http://dimplejs.org/advanced_examples_viewer.html?id=advanced_trellis_bar) I read weather, security, and carrier related data and calculated averages for each month in the give year and plotted trellis bar graph to high light the impact on the on-time performance of airlines for those months at the selected airport and year.

This initial iteration can be viewed at `index2.html`, or below:

<img src="../master/img/EDA4.PNG" />


## Feedback

To get feedback and enhance my the graphs, I first posted request on the Google+ with the [gist](https://gist.github.com/myaqoob67/1a3db6ee4a3b915eee28) location. I received one response from Mohammed Mahdi Akkouh asking me to add my presentation to [bl.ocks.org] (http://bl.ocks.org).  I completed uploading visualization but encountered an issue where the thumbnail was not displaying. Screenshot for the request on Google+ as shown below.

<img src="../master/img/Feedback_Request1.PNG" />

Unfortunately, I did not receive any further responses.  Hence, I decided to show the visualiazation to three of my colleagues at work and get their feedback and to improve the visulaization in the light of their feedback.  

### Feedback #1: Tom Pelicano

- What do you notice in the visualization?
	- I noticed carrier arrival rates by month for an airport.  I stated playing around and noticed selection can be refined by an airport and or by year.
- What questions do you have about the data?
	- I noticed the initial visualization shows one line, is that due to data?  I saw the sample data you provided below it seems there may be some abnormal sorting going on as all the points are 100%.
	- Can relationship be enhanced let say by data wrangling?
- What relationships do you notice?
	- I noticed I can relate the ups and lows of arrival rates to weather, carrier, security averages.  There is a relation but graphs stacked vertical makes is difficult to see.
- What do you think is the main takeaway from this visualization?
	- I noticed that the biggest cause of carrier delay is either carrier itself or the weather .
- Is there something you don’t understand in the graphic?
	- I noticed the graph heading is little confusing.  Can it be changed to better reflect the relationship?
	- Can the monthly graph be changed to display user friendly month names instead of numbers?


Tom's email respond's screenshot is shown below.
<img src="../master/img/Feedback1.PNG" />

### Feedback #2: Jason Yao

- What do you notice in the visualization?
	- Too Many things to look at specially the buttons.
	- Airport and year by selection idea is good, but then buttons confuses the graph output.
	- It is difficult to analyze what data points belong to which carrier in a busy graph.
- What questions do you have about the data?
	- I would like to see easier way to see the lines belonging to a carrier in the top graph.
- What relationships do you notice?
	- Carrier on-time arrival graph shows large and small carriers follow the same weather and carrier related behavior.
- What do you think is the main takeaway from this visualization?
	- I can select my airport and see which airlines scored better on on-time arrival performance .
- Is there something you don’t understand in the graphic?
	- Why the two graphs are not side by side?

Jason's email respond's screenshot is shown below.
<img src="../master/img/Feedback2.PNG" />

###  Feedback #3: Sagar Joshi

- What do you notice in the visualization?
	- Initially, the left graph only shows one straight line around 100% , but I saw changes after I started choosing different airport or year.  Initially, the top graph did not make much sense until I scroll down to second graph.
	- The buttons next to submit i.e. “Top 5 on-time” etc are unnecessary as the top graph already depict most of this relationship. I think these can be removed as these are unnecessary distraction.
- What questions do you have about the data?
	- I did not understand the what is the selection criteria for the carrier to be visible in the top graph.  Is it certain on-time threshold? And can it be added to the graph somewhere so it is not confusing.
- What relationships do you notice?
	- Carrier on-time performance is related on their on-time performance with respect to weather or carrier delay, and security doesn’t have much effect on the arrival performance.
- What do you think is the main takeaway from this visualization?
	- Carrier delay is the biggest drag on the on-time performance of the carrier.
- Is there something you don’t understand in the graphic?
	- It is difficult to see the relationships since the graphs one after the other.  One has to scroll down to see the other graph.
	- Month numbers on the second graph is not very friendly, can it be transitioned to month names instead.
	- The top graph is difficult to read as there are many lines, can airlines line graph be emphasized when it is clicked etc.?

Sagar's email respond's screenshot is shown below.
<img src="../master/img/Feedback3.PNG" />

## Post Feedback Design

I reviewed the feedback from my colleagues and marked the initial iteration to reflect the chnages that I would like to implement for the final visualization.  My changes to be implemented are mapped to the initial iteration are shown in the below image.

<img src="../master/img/Feedback_mapping.PNG" />

Summary of the changes that I am implementing to address feedback from colleagues are as follow:

- Change Month numbers to Month names.
- Move the location of the monthly category average trellis graph to the right location.
- Remove the Buttons just keep `Submit` button.  Though I will keep the source code as comments for future enhancements.
- Fix the Month number display in the `From Month` and `To Month` selection from `NaN` month numbers.
- Fix the Display on the scatter and line graph to sort flights by on-time sort order and plot those that have arrival performance of atleast 80%.
- add a `mouseover` event for the lines so it would emphasize the path to allow for better understanding of each individual carrier.
- I changed the chart title to be more consistent with the data presented.

I chose not to include the arrival data and raw numbers.  I didn't think that it was the focus of the chart, or had any impact on the understanding of airline on-time arrival rates.

Below is the final presentation of the data visualization:

<img src="../master/img/Final_visualization.PNG" />

## Coach Feedback and Design

I received excellent feedback on my visualization from the coach.  The details of the feedback is available in my github. My presentation failed on the following points and I will update my design and visualization to address these short comings:

> SPECIFICATION
> The visualization renders and any interactions or animations work as the reader interacts with the visualization.

- Remove all menu options as these makes the visualization exploratory instead of explanatory. 
- Index3.js refrenced instead of index_final.html was by mistake and will be fixed.
- Change graph title to best explain the visualization.

> SPECIFICATION
> Large code chunks are commented, and all complex code is adequately explained with comments. Comments are not overused to explain  obvious code.

- Comment the code and explain the code and purpose.
- Clean the unused code to keep it clean and crisp and easier to follow.

> SPECIFICATION
> The visualization centers on a specific, clear finding in the data.

- As per coach's recommendation, I study the data from different angles to find the interesting pattern to develop visual and title that explains it.
- I decided to compare Carrier On-Time aveage with industry average for all the years 2003-2015 and plot them. I computed industry average for each year by using rollup d3.mean() function.
- The plot was too busy to see any clear patterns to answer my question "Which airlines consistently delivered improved performance or the most punctual", as shown below:
<img src="../master/img/Post_feedback_Rendering_1A.PNG" />
- The line chart was cluttered and ineffective in displaying any distinguishable trends. I decided to refine my selection criteria.
- First, I decided to plot all carriers that did not miss a single year beating or meeting industry average and unfortunately no carriers made the cut.
- Second, The decided to plot all carriers that only missed 1 year in beating or meeting industry average and only 1 carrier made the cut i.e. "Skywest Airlines".  I don't think this is justice to other Airlines that performed as well and missed more than 1 year beating or meeting the average.
- Third, to best illustrate the top punctual airlines, I decided to adjust my decision criteriea to call airlines punctual that have not missed beating or meeting the industry average more than 4 years.  I personally think 4 years flexibility gives anough leeway to Carriers to be included that had temporary set backs and kept improving the punctuality. The result is show as below:

<img src="../master/img/Post_feedback_Rendering_1C.PNG" />

- My evaluation of this chart is that it is satisfactory in visualizing the different trends of these 5 airlines. It shows how various airlines improved over time, and which airlines were currently performing the best, as of 2015. It also showed the general trends that all 5 airlines experienced: an aggregate dip in performance from 2006 to 2008, individual peaks from 2010 to 2015. We need to keep in mind 2015 data is not complete hence final result on 2015 should not be taken as final, thought it shows the trend as the same 5 carriers are on the top list.  [skift.com](http://skift.com/2015/02/10/u-s-airlines-with-the-best-on-time-performance-in-2014/) agrees with my finding that Hawaiian Airlines and Alaska Airlines again topped the list of the most punctual U.S. airlines for full-year 2014. Those 5 airlines are the most punctual in the industry.

> SPECIFICATION
> The selected finding is clearly communicated. Design choices foster communication between the reader and the visualization.

- My evaluation of this chart is that it is satisfactory in visualizing the 5 most punctual airlines and these did not miss the industry average On-Time for more than 4 years.    


> SPECIFICATION
> The student explains initial design decisions such as chart type, visual encodings, layout, legends, or hierarchy. These are included at the beginning of the Design section in the README.md file.

- Why plot airlines that did not miss industry On-Time average more than 4 years?  During my explotary data anlysis, I used varioues thresholds of missed beating or meeting industry On-Time average years and found with 0 missed years no airlines plotted, with 1 year just 1 airline, and played the process with 2,3,4 missed years and found plotting airlines that missed only 4 years, I got the best results as it included airlines that improved better and would have been missed if I only used threshold of missing 1 year.  
- I decided that a line chart with multiple series would best show these different trends across different airlines over time. Since we are showing comparision over time, Per A. Abela, line chart is the best approach.  Coloring each line series was also a good way to visually encode and distinguish airlines from each other.
- Fix scaling in the 'On Time Percentage' axis, particularly setting the maximum at 100% to show what the disparity from the maximum, perfect on-time value.
- Overlay scatter plot points to emphasize each airline's individual data points at each year.
- Add transparency, if there considerable overlap.
- I move the legend to the right, providing close proximity to the more relevant data points. 
- I truncated the y-axis minimum at a non-zero value; I chose to truncate it at 50%, as I was concerned that a 0-100% scale would have crowded the lines and obfuscated any trends.


## Post Coach Feedback Visulization

After working on the feedback from my coach, I prepared the final visualization as shown below: 

<img src="../master/img/visualization_final.PNG" />

## Resources

- [Alberto Cairo three steps](http://vizwiz.blogspot.com/2013/01/alberto-cairo-three-steps-to-become.html)
- [Data Visualization and D3.js (Udacity)](https://www.udacity.com/course/viewer#!/c-ud507-nd)
- [dimple.js](http://dimplejs.org/)
- [Michael Bostock's bar Chart](http://bost.ocks.org/mike/bar/)
- [Scott Murray's Tutorial: D3 Chaining Methods](http://alignedleft.com/tutorials/d3/chaining-methods)
- [Mike Bostock's on Nested Selection](http://bost.ocks.org/mike/nest/)
- [Andrew Abela's Chart Suggestions](http://www.extremepresentation.com/uploads/documents/choosing_a_good_chart.pdf)
- [skift.com best 2014 airlines](http://skift.com/2015/02/10/u-s-airlines-with-the-best-on-time-performance-in-2014/)


## Data

- `data/473753677_82015_1729_airline_delay_causes.csv`: dataset

